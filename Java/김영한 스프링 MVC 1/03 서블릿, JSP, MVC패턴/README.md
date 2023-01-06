## RequestDispatcher

1. HttpServletResponse#sendRedirect()

-   두번의 HTTP 트랜잭션이 발생
-   브라우저에게 Response 후, 지정받은 요청 경로로 다시 재요청하는 방식
-   서버측에서 최초로 받은 요청 중에서 처리한 내용을 리다이렉트 된 요청안에서 공유할 수 없음
-   현재 처리중인 서브릿이 속해 있는 웹 어플리케이션 이외의 다른 자원의 경로를 요청할 수 있음

2. RequestDispatcher란

-   클라이언트로부터 최초에 들어온 요청을 JSP/Servlet 내에서 원하는 자원으로 요청을 넘김
-   서버측에서 최초로 받은 요청 중에서 처리한 내용을 리다이렉트 된 요청안에서 공유할 수 있음
-   현재 처리중인 서브릿이 속해 있는 웹 어플리케이션 범위 내에서만 요청을 제어할 수 있음

3. RequestDispatcher.forward()

-   대상 자원으로 제어를 넘기는 역할

4.  참고

-   https://dololak.tistory.com/502
