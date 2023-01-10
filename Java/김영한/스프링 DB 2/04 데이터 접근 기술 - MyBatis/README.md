## application.properties 설정

-   mybatis.type-aliases-package=hello.itemservice.domain: 마이바티스에서 타입 정보를 사용할 때는 패키지 이름을 적어주어야 하는데, 여기에 명시하면 패키지 이름을 생략할 수 있음
-   mybatis.configuration.map-underscore-to-camel-case=true: 언더바를 카멜로 자동 변경해주는 기능을 활성화
-   logging.level.hello.itemservice.repository.mybatis=trace: 실행되는 쿼리 로그를 확인

## Mapper

-   Mapping 파일에 있는 SQL을 자바 인터페이스를 통해 호출할 수 있도록 해줌
-   참고: https://hyejin.tistory.com/261

## @Param

-   Mybatis의 SQL문장에 다수의 파라미터를 전달할 때는 전달되는 변수들에 @Param 어노테이션을 붙여줘야 함
-   참고: https://dblee.tistory.com/145
