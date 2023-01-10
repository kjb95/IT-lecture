## MVC 구조

1. Dispatcher Servlet

-   모든 요청을 가장 먼저 받는 프론트 컨트롤러
-   공통적인 작업을 먼저 처리한 후에 해당 요청을 처리해야하는 컨트롤러를 찾아서 작업을 위임
-   요청에 대한 컨트롤러를 찾을 수 없는 경우, resource 경로를 탐색하여 자원을 탐색

2. HandlerMapping: 클라이언트의 요청 URL을 어떤 컨트롤러가 처리할지 결정
3. HandlerAdapter: 컨트롤러를 처리할 수 있는 어댑터를 찾아서 반환
4. ViewResolver: 뷰를 결정

5. 참고

-   https://mangkyu.tistory.com/18
-   https://chinggin.tistory.com/586