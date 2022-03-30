![](https://images.velog.io/images/mimmimmu/post/9211961b-af69-4519-96b7-3442f9b2d30a/image.png)
# HTTP STATUS CODE란?
- 서버로 보낸 요청 상태를 나타내는 코드
- 서버로 보낼 작업의 수행상태를 알려줄 수 있도록 표준에 맞춘 일종의 약속

## 종류
1. 1xx(정보) : 서버가 요청을 받았으며 서버에 연결된 클라이언트는 작업을 계속 진행하라는 의미
2. 2xx(성공) : 요청을 성공적으로 받아서 처리했다는 의미
3. 3xx(리다이렉션) : 요청 완료를 위해 추가 작업 조치가 필요한 경우
4. 4xx(클라이언트 오류) : 클라이언트 오류, 요청의 문법이 잘못되었거나 요청을 처리할 수 없는 경우
5. 5xx(서버 오류) : 서버가 유효한 요청을 처리하는 데 실패한 경우

## 주요한 세부 종류
### 2xx
> Successful Response

1. 200 OK : 요청 성공
2. 201 Created : 요청을 성공하여 새로운 리소스가 생성된 경우
	- http method post에 대한 응답에서 볼 수 있음
3. 202 Accepted : 요청이 접수되었으나 처리가 완료되지 않았을 경우
4. 204 no content : 서버가 요청을 성공적으로 수행했지만 응답 페이로드 본문에 보낼 데이터가 없는 경우
### 4xx
> 클라이언트 측에서 잘못된 요청 및 데이터를 보내고 있기 때문에 재시도를 하더라도 똑같이 실패하는 경우

1. 400 bad request : 클라이언트가 잘못된 문법으로 요청을 하여 서버가 처리할 수 없는 경우
2. 401 unauthorized : 클라이언트가 해당 리소스에 대한 인증이 필요한 경우
	- 보통 로그인이 필요한 페이지에 대해 이 요청을 제공함
3. 403 forbidden : 서버가 요청을 이해했지만 승인을 거부한 상황
	- 401과 달리 서버가 클라이언트가 누구인지를 알고 있지만 접근 권한이 불충분한 경우에 주로 사용
4. 404 not found : 요청 리소스를 찾을 수 없는 경우
	- 서버와 통신은 되지만 페이지가 사라진 경우와 같이 클라이언트가 요청한 바를 찾을 수 없는 경우 사용
### 5xx
> 서버 문제로 오류가 발생한 상황, 재시도하면 경우에 따라 성공할 수도 있음

1. 500 internal server error : 서버 내부 문제로 오류가 발생
	- 웹사이트 서버에 문제가 있음을 의미하지만, 서버가 정확한 문제에 대해 구체적으로 설명할 수 없는 상황
2. 502 bad gateway : 서버가 게이트웨이로부터 잘못된 응답을 수신한 경우
	- 인터넷 상의 서버가 다른 서버로부터 유효하지 않은 응답을 받은 경우에 발생
3. 503 service unavailable : 서비스 이용불가
	- 서버가 일시적인 과부하 또는 유지보수와 같은 예정된 작업으로 인해 잠시 요청을 처리할 수 없는 경우
4. 504 gateway timeout : 게이트웨이에 연결된 서버로부터 응답을 적절한 시간 내에 받을 수 없는 경우
	- 대개 인터넷 상의 서버간의 네트워크 오류이거나 서버의 문제일 가능성이 큼
    