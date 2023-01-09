## @EventListener(ApplicationReadyEvent.class)

-   스프링은 애플리케이션이 구동되어 서비스 요청을 받을 준비가 되었을때 ApplicationReadyEvent 이벤트를 발생
-   @EventListener(ApplicationReadyEvent.class)를 사용하면 스프링이 구동될때 코드를 실행시킬 수 있음
-   참고: https://madplay.github.io/post/run-code-on-application-startup-in-springboot

## @Profile

-   스프링에서는 프로필을 통해 런타임 환경을 설정할 수 있는 기능을 제공
-   테스트 환경에서 여러 테스트를 돌리고 난 다음 배포 환경으로 전환하는 것을 도와주는 기능
-   @Profile 어노테이션을 통해 스프링 환경설정을 할 수 있음
-   참고: https://engkimbs.tistory.com/712