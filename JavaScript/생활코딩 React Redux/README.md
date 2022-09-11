## Provider

-   Provider 컴포넌트의 하위 컴포넌트들이 Provider를 통해 Redux의 store에 접근할 수 있는 권한을 얻게 해줌

## connect(mapStateToProps, mapDispatchToProps)(Home)

-   Redux의 store에 연결 시켜 줌
-   mapStateToProps : store의 state를 가져와서 컴포넌트의 props로 보냄
-   mapDispatchToProps : store의 dispatch를 props로 보냄
-   Home : 얻은 데이터를 props로 사용하고 싶은 컴포넌트를 지정
