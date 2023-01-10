## @Bean, @Configuration, @Component

1. Spring Bean의 구성 요소

-   id: Bean의 고유 식별자
-   scope: Bean을 생성하기 위한 방법(singleton, prototype 등)
-   constructor-arg: Bean 생성 시 생성자에 전달할 파라미터
-   property: Bean 생성시 세터메소드에 전달할 인수

2. @Bean, @Configuration

-   메소드에 @Bean을 붙여 수동으로 스프링 컨테이너에 빈을 등록
-   @Configuration을 붙인 클래스에서, @Bean에 등록된 클래스는 싱글톤을 보장받을 수 있음
-   @Bean을 사용해 수동으로 빈을 등록해줄 때에는 메소드 이름으로 빈이름이 결정됨
-   개발자가 직접 제어가 불가능한 라이브러리를 빈으로 등록할때만 사용

3. @Component

-   스프링은 @Component 어노테이션이 있는 클래스들을 찾아서 빈으로 등록
-   스프링은 컴포넌트 스캔을 이용한 자동 빈 등록 방식을 권장

4.  참고

-   https://mangkyu.tistory.com/75

## 스프링 컨테이너

1. BeanFactory

-   스프링 컨테이너의 최상위 인터페이스
-   스프링 빈을 관리하고 조회하는 역할을 함

2. ApplicationContext

-   BeanFctory의 하위 인터페이스로, BeanFactory에 부가기능을 추가한 것

3. 스프링 컨테이너

-   컨테이너 내부에는 key는 빈 이름, value로는 실제 빈 객체 형태의 빈 저장소가 존재
-   빈을 싱글톤으로 관리

4. AnnotationConfigApplicationContext

-   스프링 컨테이너의 구현체
-   설정 클래스를 파라미터로 넘겨주면, 설정 클래스 내부의 @Bean 어노테이션이 붙은 메소드들을 실행하면서 빈 저장소에 실제 빈을 등록
-   빈을 사용할땐, 메소드 이름을 통해 객체를 가져올 수 있음

5.  참고

-   https://velog.io/@max9106/Spring-ApplicationContext
