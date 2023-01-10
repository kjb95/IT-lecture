## JDBC

-   Java Database Connectivity
-   자바와 데이터베이스를 연결하기 위한 JAVA 표준 SQL 인터페이스

1. Connection Pool

-   Pool 속에 데이터베이스와 연결할 Connection 객체를 미리 여러개 만들어 둠
-   데이터베이스에 접근 요청이 왔을 때 그중 하나의 Connection 객체를 할당하여 사용
-   사용이 종료되면 Connection 객체를 반납

2. DataSource

-   DB Driver 연결, Connection 객체를 관리하는 역할을 하는 인터페이스

3. 참고

-   https://wildeveloperetrain.tistory.com/125

## Statement, PreparedStatement 클래스

1. Statement 클래스

-   Connection.createStatement() 메소드를 호출하여 생성
-   executeQuery() 메소드를 호출하여 SQL문을 실행
-   정적인 쿼리문을 처리할 수 있음
-   SQL문을 실행할 때마다 SQL문을 매 번 새로 작성하고 해석해야 하므로 오버헤드가 큼

2. PreparedStatement 클래스

-   Connection.prepareStatement() 메소드를 호출하여 생성
-   쿼리문의 인수에 대한 위치홀더는 ?로 표현함
-   SQL문을 미리 준비해 놓고 위치홀더 ?에 바인딩 변수를 넣어 같은 형태의 SQL문을 쉽게 처리

3. 참고

-   https://velog.io/@dingdoooo/JDBC-Statement-PreparedStatement-%EC%9D%B4%EC%9A%A9%ED%95%98%EA%B8%B0

## ResultSet 인터페이스

-   SELECT문을 executeQuery() 메소드로 실행한 다음 반환되는 결과를 저장
-   모든 데이터를 한번에 가져올 수 없기 때문에 cursor의 개념을 가짐
-   next() 메소드가 커서를 이동시킴
-   참고: https://codedragon.tistory.com/5975

## RowMapper

-   쿼리문의 결과를 데이터형이 아닌 객체로 받을수 있도록 도와주는 함수형 인터페이스
-   ResultSet의 값을 담아와서 객체에 저장
-   참고: https://conanglog.tistory.com/35

## JdbcTemplate

-   JDBC API의 구조적인 반복을 줄이기 위해 만들어진 클래스
-   query() 메소드는 파라미터로 전달받은 쿼리를 실행하고, RowMapper 클래스를 이용하여 ResultSet의 결과를 자바 객체로 변환
-   참고: https://jaehoney.tistory.com/34

## SimpleJdbcInsert

-   삽입된 데이터의 primary key를 쉽게 얻을수 있게 도와줌
-   참고: https://github.com/benelog/spring-jdbc-tips/blob/master/spring-jdbc-core.md

## JPA, Hibernate, Spring Data JPA

1. JPA

-   Java Persistence API
-   자바 어플리케이션에서 관계형 데이터베이스를 사용하는 방식을 정의한 인터페이스

2. Hibernate

-   JPA의 구현체
-   JPA에서 명시해둔 인터페이스를 직접 구현한 라이브러리

3. Spring Data JPA

-   JPA를 쓰기 편하게 만들어놓은 모듈
-   JPA를 이용한 Repository 인터페이스를 제공

4. 참고

-   https://suhwan.dev/2019/02/24/jpa-vs-hibernate-vs-spring-data-jpa/

## Entity, DAO, Repository

1. Entity

-   실제 DB의 테이블과 매칭될 클래스

2. DAO

-   Data Access Object
-   실제로 DB에 접근하는 객체
-   SQL을 사용하여 DB에 접근한 후 적절한 CRUD API를 제공
-   퍼시스턴스 레이어에 속함
-   데이터 지속성의 추상화

3. Repository

-   도메인 레이어에 속하여, DAO를 사용할 수 있음
-   객체 컬렉션의 추상화

4. 참고

-   https://gmlwjd9405.github.io/2018/12/25/difference-dao-dto-entity.html
-   https://devlopsquare.tistory.com/106

## EntityManager

-   엔티티를 관리하는 역할을 수행하는 클래스
-   내부에 PersistenceContext를 두어 엔티티를 관리

1. Transaction

-   오류가 났을 때 처음 상태로 롤백하는 작업의 단위
-   트랜잭션이 모두 정상적으로 수행됐을 때는 commit을 수행하여 작업 내용을 실제 DB와 엔티티 매니저에 반영
-   엔티티 매니저에서 수행하는 모든 로직은 트랜잭션 안에서 수행되어야 함

2. 참고

-   https://perfectacle.github.io/2018/01/14/jpa-entity-manager-factory/
