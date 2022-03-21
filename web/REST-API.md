# REST API란

## API란

- 데이터와 기능의 집합을 제공하여 컴퓨터 프로그램간 상호작용을 촉진하며, 서로 정보를 교환가능 하도록 하는 것
- 예) 날씨 API, 소셜로그인 API 등

## REST API의 정의

- 데이터와 기능의 집합을 제공하여 컴퓨터 프로그램간 상호작용을 촉진하며, 서로 정보를 교환가능 하도록 하는 것
- 최근 OpenAPI, 마이크로 서비스 등을 제공하는 업체 대부분은 REST API를 제공한다.

## REST 구성

- 자원(RESOURCE) - URI
- 행위(Verb) - HTTP METHOD
- 표현(Representation)

# REST API 설계 규칙

## 중심규칙

1. URI는 정보의 자원을 표현해야한다.
    1. 리소스명은 동사보다는 명사를 사용한다
2. 자원에 대한 행위는 HTTP Method(GET, POST, PUT, DELETE)로 표현한다.

```java
GET /members/delete/1 (X) -> delete와 같은 행위 표현 X
GET /members/1 (O)
```

### [참고]HTTP Method

| METHOD | 역할 |
| --- | --- |
| POST | 리소스 생성 |
| GET | 리소스 조회 |
| PUT | 리소스 수정 |
| DELETE | 리소스 삭제 |

## 세부규칙

1. 슬래시 구분자(/)는 계층 관계를 나타낼 때 사용한다.
    1. `http://restapi.example.com/houses/apartments`
2. URI 마지막 문자로 슬래시(/)를 포함하지 않는다
    1. URI에 포함되는 모든 글자들은 리소스의 유일한 식별자로 사용
        
        ⇒  URI가 다르다는 것 = 리소스가 다르다는 것 
        
        ⇒  리소스가 다르다면 URI도 달라져야 한다
        
    2. 분명한 URI를 만들어 통신에 혼동을 주지 않도록 URI 경로의 마지막에는 슬래시를 사용하지 않는다
    3. `http://restapi.example.com/houses/apartments/ (X)`
3. URI 가독성을 높이기 위해 하이픈(-)을 사용
4. 언더바(_)는 URI에 사용하지 않는다
    1. 언더바는 보기 어렵고 문자가 가려지기도 하기 때문에 가독성을 위해 사용하지 않는다
5. URI 경로에는 소문자가 적합하다
    1. RFC 3986(URI 문법 형식)은 URI 스키마와 호스트를 제외하고는 대소문자를 구별하도록 규정하기 때문
6. 파일 확장자는 URI에 포함하지 않는다.
    - 대신 Accept header를 사용한다.
    - `http://restapi/example.com/members/soccer/345/photo.jpg (X)`
    - `GET /members/soccer/345/photo HTTP/1.1 Host:[restapi.example.com](http://restapi.example.com) Accept: image/jpg (O)`
7. 리소스 간에 연관관계가 있는 경우에는
    - `/리소스명/{리소스ID}/관계있는 다른 리소스명` 의 형식
    - `GET : /users/{userid}/devices (일반적으로 소유(has)관계 표현할 때)`

# HTTP 응답상태 코드

| 상태코드 |  |
| --- | --- |
| 200 | 정상 수행 |
| 201 | 리소스 생성 요청시 성공적으로 리소스 생성(POST) |

| 상태코드 |  |
| --- | --- |
| 400 | 클라이언트의 요청이 부적절한 경우 |
| 401 | 클라이언트가 인증되지 않은 상태에서 보호된 리소스를 요청했을 때 (로그인하지 않은 유저가 로그인한 경우에만 요청 가능한 리소스를 요청했을 시) |
| 403 | 유저 인증상태와 관계없이 응답하고 싶지 않은 리소스를 클라이언트가 요청했을 때 (403보다는 400이나 404 사용 권장. 403 자체가 리소스가 존재한다는 뜻이므로) |
| 405 | 클라이언트가 요청한 리소스에서는 사용불가능한 메소드를 이용했을 경우 |

| 상태코드 |  |
| --- | --- |
| 301 | 클라이언트가 요청한 리소스에 대한 URI가 변경되었을 경우(응답 시 Location header에 변경된 URI를 적어줘야 함) |
| 500 | 서버에 문제가 있을 경우 |
