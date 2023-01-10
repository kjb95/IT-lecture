## AOP

-   Aspect Oriented Programming

1. AOP 용어

-   CC(Core Concern): 주 관심사항
-   CCC(Cross Cutting Concern): 공통 관심사항
-   Joinpoint: 인스턴스의 생성시점과 메소드를 실행하는 시점
-   Pointcut: 어떠한 Joinpoint에 적용되어야 하는지 정의
-   Aspect: CCC를 모듈화 한것
-   Advice: 공통 기능의 코드를 의미하며, Aspect의 실제 구현체

2. Proxy

-   프록시는 핵심 기능을 구현하지 않음
-   프록시는 여러 객체에 공통으로 적용할 수 있는 기능을 구현
-   스프링 AOP는 런타임에 프록시 객체를 생성해서 공통 기능을 삽입

3. Advice 동작 시점

1) Before  
   대상 객체의 메소드 호출 전에 공통 기능을 실행
2) After Returning  
   대상 객체의 예외발생 없이 실행된 이후에 공통 기능을 실행
3) After Throwiong  
   대상 객체의 메소드를 실행하는 도중 예외가 발생한 경우에 공통 기능을 실행
4) After
   예외 여부 상관없이, 메소드 실행 후 공통기능을 실행
5) Around
   대상 객체의 메소드 실행 전, 후 또는 예외 발생 시점에 공통 기능을 실행

4. 참고

-   https://engkimbs.tistory.com/746
-   https://darmk.tistory.com/entry/Spring-12-AOP-%EA%B8%B0%EB%B3%B8-%EA%B0%9C%EB%85%90-CC-CCC-Joinpoint
-   https://owin2828.github.io/devlog/2019/12/30/spring-7.html

## ProceedingJoinPoint

-   Around Advice에서 사용할 공통 기능 메소드는 대부분 파라미터로 전달받은 ProceedingJoinPoint의 proceed() 메서드만 호출하면 됨

-   https://ktko.tistory.com/entry/Spring-ProceedingJoinPoint%EC%9D%98-%EB%A9%94%EC%84%9C%EB%93%9C
