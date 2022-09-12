## Proxy Server

-   클라이언트가 자신을 거쳐 다른 네트워크에 접속할 수 있도록 중간에 대리 해주는 서버

## Cache Server

-   클라이언트가 요청한 컨텐츠들을 기억하고 있다가 어느 한 클라이언트가 웹 캐시 서버가 기억하고 있는 동일한 컨텐츠를 또 다시 요청하는 경우 이를 직접 응답하여 웹 서버의 부하를 절감시켜 주는 역할을 함
-   프록시 서버와 동작 방식이 같음

## CDN

-   Content Delivery Network
-   서버를 분산시켜 캐싱 해두고 사용자의 컨텐츠 요청이 들어오면 사용자와 가장 가까운 위치에 존재하는 서버로 매핑시켜 요청된 컨텐츠의 캐싱된 내용을 내어주는 방식으로 빠르게 데이터를 전송
-   Static Caching : Origin Server에 있는 Content를 운영자가 미리 Cache Server에 복사
-   Dynamic Caching : 사용자가 Content 요청 시 Content가 있으면 캐싱된 Content를 전달하고 없으면 Origin Server로 부터 Cacher Server에 복사