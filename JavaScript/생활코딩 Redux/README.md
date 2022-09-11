## Action

-   하나의 객체로 표현되며, 상태에 어떠한 변화가 필요하게 될때 발생 시킴
-   Action 객체는 type 필드를 필수적으로 가지며, 그 이외의 값들은 마음대로 넣을 수 있음
-   Action Creator : Action을 생성하는 함수

## Reducer

-   이전의 state와 action을 인자로 전달 받는 함수로, 새로운 state를 반환 함

## Store

-   리덕스는 한 애플리케이션 당 하나의 Store를 만들 수 있음
-   dispatch() : Action을 발생시키는 함수로, action을 인자로 전달 받음
-   subscribe() : 인자로 전달받은 함수는 dispatch()가 호출될 때 마다 호출 됨
