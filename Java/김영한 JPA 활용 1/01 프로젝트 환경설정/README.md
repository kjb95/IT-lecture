## H2 데이터베이스 설치

-   처음 데이터 베이스 설정시: jdbc:h2:~/jpashop(JDBC URL)
-   ~/jpashop.mv.db 파일 확인
-   처음 이후로는 jdbc:h2:tcp://localhost/~/jpashop(JDBC URL)로 데이터베이스 연결

## Hibernate

1. Hibernate Framework Layer

-   데이터베이스와 응용 프로그램 사이의 레이어
-   애플리케이션과 데이터베이스 간의 데이터를 동기화하는 영속 객체를 생성
-   Hibernate는 데이터를 데이터베이스에서 유지하기 위해 엔티티 클래스의 인스턴스를 생성

2. SessionFactory

-   객체를 데이터베이스에 유지하려면 SessionFactory 인터페이스의 인스턴스가 필요함
-   팩토리 디자인 패턴을 구현한 싱글톤 인스턴스
-   Session 객체를 얻기위한 팩토리 메소드를 제공

3. Session

-   응용 프로그램과 데이터베이스에 저장된 데이터간의 인터페이스를 제공
-   수명이 짧은 객체이며, JDBC연결을 래핑

4.  참고

-   https://joosjuliet.github.io/hibernate_structure/

## Spring Boot application 속성 정의

1. spring.jpa.hibernate.ddl-auto: create

-   JPA에서느 기본적으로 Entity에 테이블을 매핑하면 쿼리를 사용하지 않고 값을 가져올 수 있음
-   create 옵션: SessionFactory 시작시 스키마를 삭제하고 다시 생성

2. spring.jpa.properties.hibernate.show_sql=true

-   Hibernate가 db에 날리는 모든 쿼리를 보여 줌

3. spring.jpa.properties.hibernate.format_sql=true

-   보여지는 쿼리를 예쁘게 포맷팅 해줌

4. 참고

-   https://haservi.github.io/posts/spring/hibernate-ddl-auto/
-   https://lannstark.tistory.com/14

## @PersistenceContext

-   EntityManager를 빈으로 주입할 때 사용하는 어노테이션
-   참고: https://batory.tistory.com/497

## Transaction

1. 트랜잭션의 필요성

-   작업을 진행하다가 문제가 생겼을 경우, 이전 상태로 롤백하기 위해 사용
-   더 이상 쪼갤 수 없는 최소 단위를 의미
-   트랜잭션은 커밋으로 성공하거나 롤백으로 실패 이후 취소되어야 함

2. 트랜잭션 동기화

-   트랜잭션을 시작하기 위한 Connection 객체를 특별할 저장소에 보관해두고 필요할 때 거내쓸 수 있도록 하는 기술
-   각 쓰레드마다 Connection 객체를 독립적으로 관리하기 때문에 멀티쓰레드 환경에서도 충돌이 발생할 여지가 없음
-   JDBC가 아닌 Hibernate에서는 Connection이 아닌 Session이라는 객체를 사용하기 때문에, 트랜젝션 동기화 코드들이 문제를 발생시킴
-   Hibernate 사용시 트랜잭션 추상화를 해야 함

3. 트랜잭션 추상화

-   각 기술(JDBC, Hibernate 등) 종속적인 코드를 이용하지 않고도 일관되게 트랜잭션을 처리할 수 있도록 도와줌

4. AOP를 이용한 트랜잭션 분리

-   @Transactional: 비즈니스 로직 코드에서 트랜잭션 코드를 분리하여 별도의 모듈로 만드는 AOP 기술를 적용한 어노테이션

5. Spring 트랜잭션의 세부 설정

1) 트랜잭션 전파
   트랜잭션의 경계에서 이미 진행중인 트랜잭션이 있거나 없을때 어떻게 동작할 것인가를 결정하는 방식
2) 격리 수준
   모든 트랜잭션의 격리 수준을 적절하게 조정해서 가능한 많은 트랜잭션을 동시에 진행시키면서 문제가 발생하지 않도록 제어해야 함
3) 제한시간
   트랜잭션을 수행하는 제한시간을 설정
4) 읽기전용
   트랜잭션 내에서 데이터를 조작하는 시도를 제한

6. 참고

-   https://mangkyu.tistory.com/154

## 트랜잭션의 세부 설정

1. 전파 속성

-   https://mangkyu.tistory.com/169

## 영속성 컨텍스트, 플러시

1. EntityManagerFactory, EntityManager

-   JPA는 매 요청마다 EntityManagerFactory에서 EntityManager를 생성
-   EntityManager는 내부적으로 DB 커넥션 풀을 사용해서 DB와 연결

2. 영속성 컨텍스트

-   엔티티를 영구적으로 저장하는 환경
-   엔티티 매니저를 통해 영속성 컨텍스트에 접근

3. 엔티티의 생명주기

1) 비영속
   영속성 컨텍스트와 관계가 없는 상태
2) 영속
   영속성 컨텍스트에 저정된 상태
   엔티티가 영속성 컨텍스트에 의해 관리됨
   아직은 데이터베이스에 저장되지 않은 상태
   트랜잭션의 커밋 시점에 영속성 컨텍스트에 있는 정보들이 DB에 쿼리로 날라감
3) 준영속
   영속성 컨텍스트에 저장되었다가 분리된 상태

4) 삭제
   삭제된 상태

4. 플러시

-   영속성 컨텍스트의 변경 내용을 데이터베이스에 반영
-   트랜잭션 커밋이 일어날 때 플러시가 동작하는데, 쓰기 지연 저장소에 쌓아 놨던 쿼리들이 데이터베이스에 날라감

5. 참고

-   https://ict-nroo.tistory.com/130

## 기본 키 매핑

-   모든 엔티티는 고유의 기본 키를 가져야 함
-   JPA는 @Id 어노테이션ㅇ로 기본 키 매핑을 지원

1. @GeneratedValue

-   기본키를 자동 생성 하기 위해 사용하는 어노테이션
-   속성값에 따라 자동 생성 방식이 다름

2. IDENTITY

-   기본 키 생성을 데이터베이스에 완전히 위임
-   예를 들어서, MySQL에서는 IDENTITY 사용시 AUTO_INCREMENT 기능을 사용

3. SEQUENCE

-   시퀀스: 유일한 값을 순서대로 생성하는 객체
-   시퀀스 기능을 활용하여 엔티티에 식별자를 할당

4. TABLE

-   키 생성 전용 테이블을 하나 만들어서 시퀀스를 흉내 낸것

5. AUTO

-   선택한 DB에 따라 IDENTITY, SEQUENCE, TABLE 전략 중 하나를 자동으로 선택
-   @GeneratedValue의 기본값

6. 참고

-   https://passionate.tistory.com/58
     