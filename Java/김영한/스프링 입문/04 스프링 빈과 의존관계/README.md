## POJO

-   Plain Old Java Object
-   환경과 기술에 종속되지 않고 필요에 따라 재활용될 수 있는 방식으로 설계된 객체
-   참고: https://siyoon210.tistory.com/120

## Spring Container

1. 컨테이너

-   인스턴스의 생명주기를 관리
-   생성된 인스턴스에게 추가적인 기능을 제공

2. Servlet Container

-   클라이언트의 요청을 처리하고, 그 결과를 반환하는 서블릿의 생명주기를 관리
-   예시) 톰캣

3. Spring Container

-   자바 Bean 객체들의 생명주기를 개발자를 대신하여 관리
-   의존성 있는 컴포넌트들 간의 관계를 개발자가 직접 코드로 명시하지 않고 스프링 컨테이너가 대신 연결

4. Spring Container 종류

1) BeanFactory  
   빈을 관리하는 기능을 담당  
   빈의 정의는 즉시 로딩하지만, 빈 자체가 필요하기 전까지는 인스턴스화 하지 않음  
   getBean()이 호출되어야, 의존성 주입을 이용해 빈을 인스턴스화 함
2) ApplicationContext  
   빈 팩토리를 상속하여, 기본적인 기능은 빈 팩토리와 동일  
   스프링이 제공하는 각종 부가 서비스를 추가로 제공  
   빈 팩토리와 다르게, 싱글톤 빈을 미리 인스턴스화 함

5.  참고

-   https://jobjava00.github.io/language/java/framework/spring/container/

## Spring Bean

-   스프링 컨테이너에 의해 관리되는 자바 객체(POJO)

1. Component Scan

-   개발자가 직접 컨트롤이 가능한 클래스 또는 인터페이스를 빈으로 등록할때 사용
-   @Component가 붙은 클래스를 스프링 빈으로 등록

2. 자바 코드로 등록

-   개발자가 컨트롤이 불가능한 외부 라이브러리들을 빈으로 등록할때 사용
-   @Configuration가 붙은 클래스에서, @Bean이 붙은 메소드가 생성하는 인스턴스를 스프링 빈으로 등록

3. 빈 스코프

1) Singleton  
   스프링 컨테이너에서 한번만 생성되며, 컨테이너가 사라질 때 제거됨
   기본적으로 모든 빈은 스코프가 명시적으로 지정되지 않으면 싱글톤으로 관리됨
2) Prototype
   DI가 발생할 떄마다 새로운 객체가 생성되어 주입됨  
   빈 소멸을 스프링 컨테이너가 관여하지 않고, GC가 관리함

4. 참고

-   https://steady-coding.tistory.com/594
