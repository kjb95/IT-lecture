## Connection Pool

-   일정량의 Connection 객체를 미리 만들어서 pool에 저장
-   프로그램에서 요청이 오면 Connection 객체를 빌려주고, 해당 객체의 임무가 완료되었으면 다시 반납 받아서 pool에 저장
-   참고: https://kimvampa.tistory.com/44

## Statement, PreparedStatement

1. Statement

-   Connection 객체의 createStatement()를 호출하여 얻음
-   쿼리문에 값이 미리 입력된 정적인 쿼리를 처리할 수 있음
-   SQL을 실행할 때마다 SQL을 매번 새로 작성해야 하므로 오버헤드가 존재

2. PreparedStatement

-   Connection 객체의 preparedStatement()를 호출하여 얻음
-   위치 홀더(?)를 사용하여 SQL을 정의할 수 있음
-   SQL문을 미리 준비해 놓고 바인딩 변수를 사용해 반복되는 SQL문을 쉽게 처리 가능

3. 참고

-   https://velog.io/@dingdoooo/JDBC-Statement-PreparedStatement-%EC%9D%B4%EC%9A%A9%ED%95%98%EA%B8%B0

## ResultSet

-   SELECT문의 결과를 저장하는 객체
-   참고: https://joomal.github.io/210105resultset/
