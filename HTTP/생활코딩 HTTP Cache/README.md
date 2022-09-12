## Cache-Control 헤더의 옵션

-   no-store : 캐시를 사용하지 않음
-   maxAge : 캐시의 만료시간 설정
-   no-cache : maxAge=0과 같은 의미

## Last-Modified

-   리소스가 마지막으로 수정된 날짜와 시각을 담은 HTTP 응답 헤더
-   ETag 헤더보다는 덜 정확하지만, 대비책으로 사용 됨
-   If-Modified-Since : 리소스가 수정 되었는지 확인하는 HTTP 요청 헤더

## ETag

-   리소스가 변경되었는지 식별자 역할을 하는 HTTP 응답 헤더
-   If-None-Match : ETag가 다를 경우에만 요청을 처리하는 HTTP 요청 헤더