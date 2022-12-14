## /pages/\_app.js

-   서버로 요청이 들어왔을 때 가장 먼저 실행되는 컴포넌트
-   모든 컴포넌트에 공통으로 적용할 레이아웃

## /pages/\_document.js

-   \_app.js 다음에 실행되며, 공통적으로 활용할 \<head\> 나 \<body\> 태그 안에 들어갈 내용들을 커스텀할 때 활용

## /pages/\_error.js

-   500 에러가 발생했을때 보여주는 커스텀 페이지

## SEO

-   Search Engine Optimization
-   검색 엔진으로 부터 제대로 인식이 될 수 있도록 최적화 하는 작업
-   기본적으로 해당 페이지에 적합한 메타태그를 삽입해서 크롤러가 웹을 잘 분석해서 인덱싱을 하는데 도움을 주는 방법이 있음

## Pre Rendering

-   NextJS는 기본적으로 모든 페이지를 미리 만듬
-   퍼포먼스 향상과 SEO에 유리

## Static Site Generation

-   프로젝트가 빌드하는 시점에 HTML 파일들이 생성 됨
-   매 요청 마다 미리 생성한 HTML 페이지를 재사용해 보여 줌
-   정적 생성된 페이지들은 CDN에 캐시

## Server Side Rendering

-   매 요청 마다 HTML을 생성하여 항상 최신 상태를 유지

## getStaticProps()

-   SSG 방식이며, 함수 호출 이후 얻은 데이터를 해당 컴포넌트의 props로 전달하여 렌더링
-   배포 모드에서는 빌드시 에만 동작하고, 개발 모드 에서는 매 요청 마다 동작함

## getStaticPaths()

-   SSG 방식이며, pages/\*\*/[id].js 형태의 동적 라우팅 페이지 중, 빌드 시에 static 하게 생성할 페이지를 정함
-   개발 모드에서는 매 요청마다 동작
-   fallback(false) : 함수가 반환하지 않는 페이지는 404로 연결
-   fallback(true) : 함수가 반환하지 않는 페이지를 처음 접속 시, 서버에 페이지를 생성하고, 그 다음 접속시, 생성한 페이지를 보여 줌
-   배포 모드에서는 빌드시 에만 동작하고, 개발 모드 에서는 매 요청 마다 동작함

## getServerSideProps()

-   SSR 방식이며, 함수 호출 이후 얻은 데이터를 해당 컴포넌트의 props로 전달하여 렌더링

## SPA

-   Single Page Application
-   웹 사이트에서 행동을 했을 때 전체 페이지가 로딩 되는 대신 현재 웹 페이지에서 동적으로 데이터만 바뀌게 되는 것
-   SPA 라우팅 : 서버로 요청을 전달하지 않고 자바스크립트 영역 에서 HTML5의 history API를 이용해 페이지 내에서 화면 이동이 일어난 것처럼 작동
