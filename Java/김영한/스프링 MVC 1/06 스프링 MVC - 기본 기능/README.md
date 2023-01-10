## HttpMessageConverter

1. 스프링 MVC의 HttpMessageConverter 적용

-   HTTP 요청: @RequestBody, HttpEntity(RequestEntity)
-   HTTP 응답: @ResponseBody, HttpEntity(ResponseEntity)

2. canRead(), canWrite(), read(), write()

-   canRead(), canWrite(): 메시지 컨버터가 해당 클래스 타입 혹은 미디어타입의 지원하는지 확인
-   read(), write(): 메시지 컨버터를 통해 메시지를 읽고 쓰는 기능

3. HTTP 요청 데이터 읽는 과정

1) 요청이 오면 컨트롤러에서 @RequestBody 혹은 HttpEntity 사용
2) canRead()를 호출하여 대상 클래스 타입을 지원하는지, HTTP 요청의 Content-Type 미디어 타입을 지원하는지 확인
3) canRead() 조건을 만족하는 경우 read()를 호출하여 객체 생성후 반환

4. HTTP 응답 데이터 생성하는 과정

1) 컨트롤러에서 @ResponseBody 혹은 HttpEntity로 값이 반환
2) canWrite()를 호출하여 대상 클래스 타입을 지원하는지, HTTP 요청의 Accept 미디어 타입을 지원하는지 확인
3) canWrite() 조건을 만족하는 경우 write()를 호출하여 HTTP 응답 메시지 바디 내 데이터 생성

5. ByteArrayHttpMessageConverter

-   클래스 타입: byte []
-   미디어 타입: _/_

6. StringHttpMessageConverter

-   클래스 타입: String
-   미디어 타입: _/_

7. MappingJackson2HttpMessageConverter

-   클래스 타입: 객체 또는 HashMap
-   미디어 타입: application/json

8. 참고

-   https://jaimemin.tistory.com/1823

## ArgumentResolver

-   컨트롤러 메소드의 파라미터 중 특정 조건에 맞는 파라미터가 있다면, 요청에 들어온 값을 이용해 원하는 객체를 만들어 바인딩 하는 역할

1. HandlerMethodArgumentResolver

-   ArgumentResolver는 HandlerMethodArgumentResolver를 구현해야 함
-   supportsParameter(): 주어진 메소드 파라미터의 타입이 올바른지 확인
-   resolveArgument(): 요청에 들어온 값이 원하는 객체로 바인딩

2. 참고

-   https://hudi.blog/spring-argument-resolver/

## ReturnValueHandler

-   컨트롤러에서 String으로 뷰 이름만을 반환해도 원하는 뷰로 응답해주는 역할
-   참고: https://catsbi.oopy.io/84f908e6-3a2e-42ef-8106-05728ae8447b
