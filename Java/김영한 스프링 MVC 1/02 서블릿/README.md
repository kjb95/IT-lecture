## HttpServlet

1. Servlet 동작구조

-   Servlet 클래스는 HttpServlet 클래스를 상속받아야 함
-   클라이언트 요청에 따라 서블릿 컨테이너는 service() 메소드를 호출하고, service() 메소드는 요청이 GET인지 POST인지 구분하여 각각 doGet(), doPost() 메소드를 호출

2. doGet(), doPost()

-   doGet(), doPost() 메소드는 모두 HttpServletRequest와 HttpServletResponse 객체를 매개변수로 가짐
-   매개변수인 HttpServletResponse의 setContentType() 메소드를 호출하여 응답방식을 결정
    `response.setContentType("text/html; charset=euc-kr");`
-   HttpServletResponse의 getWriter() 메소드를 이용하여 출력 스트림을 얻음
    `PrintWriter writer = response.getWriter();`
-   출력스트림의 println() 메소드를 이용하여 출력하면 웹 브라우저에 출력됨
    `writer.println("<html>");`
    `writer.println("</html>");`
    `writer.close();`

3. 참고

-   https://kimmy100b.github.io/jsp%20servlet/2020/02/13/JSP-Servlet-05/

## HttpServletRequest