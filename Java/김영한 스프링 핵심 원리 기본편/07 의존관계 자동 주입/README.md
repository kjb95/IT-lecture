## @Qualifier, @Primary

1. 같은 타입의 빈 등록시 생기는 문제

-   어노테이션을 통해 자동으로 빈을 컨테이너에 설정하는 경우, 같은 타입의 빈이 등록이 되면, 에러가 발생
-   컨테이너에게 어떤 빈을 주입해야 하는지 알려줘야 함

2. @Qualifier

-   빈에 추가 구분자를 붙여주는 방법
-   생성자에서 @Qualifier를 명시하면, 해당 구분자를 가진 빈을 주입

3. @Primary

-   여러 빈이 있을 때 @Primary을 명시한 빈을 주입해줌
-   메인 기능 빈과 서브 기능 빈이 있을 때, 메인 기능 빈에 @Primary 사용
-   @Primary 보다는 @Qualifier가 높은 우선 순위를 가짐

4. 참고

-   https://bestinu.tistory.com/58

## @Inherited

-   해당 어노테이션을 적용하면 부모클래스에 선언된 어노테이션이 자식클래스에 상속됩니다.
-   참고: https://hongsii.github.io/2018/12/12/java-annotation/
