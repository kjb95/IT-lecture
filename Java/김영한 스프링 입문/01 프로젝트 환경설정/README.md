## Groovy

-   JVM위에서 동작하는 동적 타입 프로그래밍 언어
-   java와 유사한 문법 구조
-   gradle script를 작성하기 위해 사용됨
-   참고: https://kotlinworld.com/320

## Gradle

-   groovy를 기반으로 만든 빌드 도구

1. Gradle Wrapper

-   프로젝트에서 내장된 gradle을 사용할 수 있도록 만든것
-   gradle을 설치하지 않아도 되고, 매 프로젝트마다 gradle 버전을 바꾸지 않아도 됨

2. gradlew, gradle.bat

-   내장 gradle을 이용해 실행하기 위한 환경설정 부터 실행까지 모두 수행하기 위해 만들어진 스크립트
-   gradlew: 맥, 리눅스용 스크립트
-   gradle.bat: 윈도우용 스크립트

4. 참고

-   https://kotlinworld.com/314
-   https://madplay.github.io/post/what-is-gradle
-   https://junilhwang.github.io/TIL/Gradle/GradleWrapper/

## build.gradle

-   프로젝트 객체로, java application을 빌드하게 되면 프로젝트 객체의 메소드들이 실행됨

1. Project Object

-   프로젝트 단위에서 필요한 작업을 수행하기 위해 모든 메소드와 프로퍼티를 모아놓은 객체

2. Gradle Task

-   groovy 언어로 작성되는 gradle 프로젝트의 작업 단위
-   미리 만들어져 있는 내장의 task들과 build.gradle 파일에 사용자가 정의한 사용자 정의 task로 종류가 나뉨

3. build.gradle 프로퍼티

-   프로젝트 객체를 위한 프로퍼티를 정의할 수 있음

4. build.gradle 메소드

-   프로젝트 객체를 위한 메소드를 정의할 수 있음
-   프로젝트가 빌드될때 해당 메소드를 수행하는 task에 의해 수행됨

5. 참고

-   https://sharplee7.tistory.com/7
-   https://kotlinworld.com/321

## Tomcat

-   서블릿 컨테이너만 있는 웹 어플리케이션 서버
-   톰캣은 웹서버와 연동하여 실행할 수 있는 자바 환경을 제공하여 JSP와 자바 서블릿이 실행할 수 있는 환경을 제공
-   HTTP 서버를 내장함
-   참고: https://melonicedlatte.com/2020/07/08/231200.html

## Servlet

-   클라이언트의 요청을 처리하고, 그 결과를 반환하는 자바 웹 프로그래밍 기술
-   웹서버가 동적인 페이지를 제공할 수 있도록 도와주는 어플리 케이션

1. Servlet 특징

-   html을 사용하여 요청에 응답
-   자바 쓰레드를 이용하여 동작
-   MVC 패턴에서 컨트롤러로 이용됨

2. Servlet 동작 방식

1) 사용자가 URL을 이볅하면 HTTP 요청이 서블릿 컨테이너로 전송됨
2) 요청을 받은 서블릿 컨테이너는 HttpServletRequest, HttpServletResponse 객체를 생성
3) 요청한 URL이 어느 서블릿에 대한 요청인지 찾음
4) 해당 서블릿에서 service 메소드를 호출한후 GET, POST 여부에 따라 doGet() 또는 doPost()를 호출
5) doGet() doPost() 메소드는 동적 메시지를 생성한후 HttpServletResponse 객체에 응답을 보냄
6) 응답이 끝나면 HttpServletRequest, HttpServletResponse 객체는 소멸됨

3. Servlet Container

-   서블릿을 관리해주는 컨테이너
-   클라이언트의 요청을 받아주고, 응답을 할 수 있게 웹서버와 소켓으로 통신
-   스프링부트는 서블릿 컨테이너로 톰캣을 사용

4. Servlet Container 역할

1) 웹서버와의 통신 지원  
   서블릿과 웹서버가 손쉽게 통신할 수 있게 해줌
2) 서블릿 생명주기 관리  
   서블릿의 탄생과 죽음을 관리하고, 적절하게 가비지 컬렉션을 진행
3) 멀티쓰레드 자원 및 관리  
   서블릿 컨테이너는 요청이 올 때 마다 자바 쓰레드를 생성  
   HTTP 서비스 메소드를 실행하고나면, 쓰레드는 자동으로 소멸됨
4) 선언적인 보안 관리  
   보안에 관련된 내용을 자바 클래스에 구현하지 않고, XML 같은 파일로 관리하게 해줌

5. Servlet 생명주기

1) init()
   클라이언트의 요청이 들어오면 컨테이너는 해당 서블릿이 메모리에 있는지 확인하고, 없을 경우 init() 메소드를 호출하여 적재  
   실행 중 서블릿이 변경될 경우, 기존 서블릿을 파괴하고 init()을 통해 새로운 내용을 메모리에 다시 적재
2) service()
   service() 메소드를 통해 요청에 대한 응답이 doGet()과 doPost()로 분기됨  
   이때 서블릿 컨테이너는 클라이언트 요청이 오면 HttpServletRequest, HttpServletResponse 객체를 생성
3) destory()  
   컨테이너가 서블릿에 종료 요청을 하면 destory() 메소드가 호출됨

6. 참고

-   https://mangkyu.tistory.com/14

## Web Template Engine

-   지정된 템플릿 양식과 데이터가 합쳐져서 HTML 문서를 출력하는 소프트웨어

1. Server Side Template Engine

-   HTML 코드에서 고정적으로 사용되는 부분은 템플릿으로 만들어두고, 동적으로 생성되는 부분만 템플릿의 특정 부분에 끼워 넣는 방식으로 동작
-   예시) JSP, Thymeleaf 등

2. Client Side Template Engine

-   데이터를 받아 DOM 객체에 동적으로 그려줌
-   웹 페이지 내에 여러 카테고리 중 한 부분만 변경되는 경우, 매번 템플릿을 입력하여 바꾸기보다는 변경된 부분만 대체되는 방식으로 동작
-   예시) Mustache

3. JSP

-   Java Server Page
-   HTML 코드에 자바 코드를 넣어 동적인 웹 페이지를 생성할 수 있음
-   서블릿의 형태로 변환되어 실핼됨
-   뷰에 비즈니스 로직이 포함되어 있어 복잡하고 무거워짐
-   JAR 패키징이 불가능

4. Thymeleaf

-   서블릿으로 변환되지 않아서 비즈니스 로직이 완전히 분리됨
-   SpringBoot가 자동설정을 지원
-   html과 같은 형태로 WAS없이도 브라우저에서 띄울 수 있기 때문에 JAR 패키징이 가능

5. 참고

-   https://code-lab1.tistory.com/211
-   https://suzyalrahala.tistory.com/39

## JRE

-   JAVA Runtime Enviroment
-   JVM이 자바프로그램을 실행시킬 때 반드시 필요하 라이브러리 및 필수 파일들을 가짐
-   참고: https://m.blog.naver.com/innolifes/222055607862

## JAR, WAR

-   JAVA의 jar 툴을 이용하여 생성된 압축파일
-   어플리케이션을 쉽게 배포하고 동작시킬 수 있도록 관련 파일들을 패키징해주는 것이 주 역할

1. JAR

-   Java Archive
-   자바 프로젝트를 압축한 파일
-   JRE만 가지고도 실행이 가능

2. WAR

-   Web Application Archive
-   웹 어플리케이션을 압축한 파일
-   WAR를 실행하려면 웹서버 또는 WAS가 필요

3. 참고

-   https://ifuwanna.tistory.com/224

## View Resolver

-   뷰 이름(String 타입)을 디스패처 서블릿에게 뷰 정보를 전달하는 경우 사용
-   뷰 이름으로 실제로 사용할 뷰 객체를 결정
-   참고: https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=kbh3983&logNo=220778740252
