## SELECT ~ FOR UPDATE

-   동시성 제어를 위해 특정 데이터에 대해 LOCK을 거는 기능
-   참고: https://dololak.tistory.com/446

## ThreadLocal

-   ThreadLocal 변수를 선언하면 멀티쓰레드 환경에서 각 쓰레드마다 독립적인 변수를 가지고 접근할 수 있음
-   참고: https://yeonbot.github.io/java/ThreadLocal/#threadlocal

## 트랜잭션 동기화

1. PlatformTransactionManager

-   각 DB마다 트랜잭션 접근 방법이 다르기 때문에 트랜잭션 접근의 추상화가 필요
-   PlatformTransactionManager를 통해 트랜잭션 추상화를 함

2. 트랜잭션 동기화 매니저

-   트랜잭션 매니저는 내부에서 트랜잭션 동기화 매니저를 사용
-   트랜잭션 동기화 매니저는 쓰레드 로컬을 사용

3. DataSourceUtils.getConnection()

-   트랜잭션 동기화 매니저는 관리하는 커넥션이 있으면 해당 커넥션을 반환
-   커넥션이 없으면, 커넥션을 새로 생성해서 반환

4. DataSourceUtils.releaseConnection()

-   트랜잭션 사용을 위해 동기화 된 커넥션을 닫지 않고 그대로 유지
-   트랜잭션 동기화 매니저가 관리하는 커넥션이 없는 경우 해당 커넥션을 닫음

5. 참고

-   https://ojt90902.tistory.com/863

## AOP 용어

-   Jointpoint: Advice를 적용할 수 있는 지점
-   Advice: Joinputpoint에서 실행되어야 하는 프로그램 코드
-   Pointcut: Jointpoint의 상세한 스펙을 정의한 것
-   Target: 실질적인 비지니스 로지을 구현하고 있는 코드
-   Aspect: Advice + Poincut
-   Weaving: Aspect를 해당 지점에 주입하는 과정
-   참고: https://swingswing.tistory.com/m/272
