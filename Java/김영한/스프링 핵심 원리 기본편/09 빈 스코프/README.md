## 의존관계 조회

1. DL

-   Dependency Lookup
-   Bean에 접근하기 위해 컨테이너가 제공하는 API를 이용하여 Bean을 검색하는것

2. ObjectFactory, ObjectProvider

-   스프링에서 제공하며, 지정한 빈을 컨테이너에서 대신 찾아주는 DL을 제공하는 클래스
-   ObjectProvider는 ObjectFactory를 상속받아 편의 기능을 추가한 클래스

3. JSR-330 Provider

-   자바 표준으로, 지정한 빈을 컨테이너에서 대신 찾아주는 DL을 제공하는 클래스

3. 참고

-   https://devmoony.tistory.com/100
-   https://dlagusgh1.tistory.com/668
-   https://developer-hm.tistory.com/44

## 웹 스코프

-   웹 환경에서만 동작하는 스코프

1. 웹스코프 종류

-   request: HTTP 요청 하나가 들어오고 나갈떄까지 유지되는 스코프
-   session: HTTP Session과 동일한 생명 주기를 가지는 스코프
-   application: 서블릿 컨텍스트와 동일한 생명주기를 가지는 스코프
-   websocket: 웹 소켓과 동일한 생명 주기를 가지는 스코프

2. 참고

-   https://dodeon.gitbook.io/study/kimyounghan-spring-core-principle/09-bean-scope/web-scope

## HttpServletRequest, HttpServletResponse

1. WAS가 웹브라우저로부터 서블릿 요청을 받으면

-   요청을 받을 때 전달 받은 정보를 바탕으로 HttpServletRequest 객체를 생성하여 저장
-   웹 브라우저에게 응답을 돌려줄 빈 HttpServletResponse 객체 생성
-   생성된 HttpServletRequest와 빈 HttpServletResponse를 서블릿에게 전달

2. HttpServletRequest

-   HTTP 프로토콜의 request 정보를 서블릿에게 전달하기 위한 목적으로 사용
-   Header, Parameter, Cookie, URI, URL 등의 정보를 읽어들이는 메소드를 가진 클래스
-   Body의 Stream을 읽어들이는 메소드를 가짐

3. HttpServletResponse

-   서블릿은 HttpServletResponse 객체에 Content Type, 응답코드, 응답 메시지 등을 담아서 클라이언트에게 전송

4. 참고

-   https://zester7.tistory.com/33
