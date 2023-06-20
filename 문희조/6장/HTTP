## HTTP 헤더 
### 6.1 HTTP 메시지 헤더
- 요청과 응답에는 포함되어있는 헤더에 각각을 처리하기 위한 정보가 들어있다.
- 그 중 ***공통적인 부분을 HTTP 메시지 필드***라고 부른다.

### 6.2 HTTP 헤더 필드
- 부가적으로 중요한 정보와 메시지 크기나 언어, 인증 정보 등을 제공한다.
- `헤더 필드 명: 필드 값`으로 구성되어 있다.
- 4종류의 헤더 필드가 존재 (General, Request, Response, Entity)
- 책에서 보여준 헤더 필드(47개) 외에도 존재
- 데이터에 따라 헤더가 두 가지로 나뉜다.
  - E2E : 이 카테고리의 헤더는 최종 목적지까지 보존된다.
  - Hop-By-Hop : 한번의 전송에 대해서만 유효하다.

### 6.3 HTTP/1.1 일반 헤더 필드
- Request와 Response 양쪽에서 사용되는 헤더이다.
#### 6.3.1 Cache-Control
- `디렉티브`라는 명령을 통해서 Cache를 컨트롤한다.
- 요청과 응답에 따라 `디렉티브`의 종류가 다르다. 다음 3개 외에도 다양하게 존재한다.
  - public : ***모든 유저***에게 Cache를 돌려줄 수 있게 한다.
  - private : ***특정 유저***에게만 Cache를 돌려줄 수 있게 한다.
  - no-cache : 요청할 때는 오리진 데이터를 받아오고, 응답할 때는 캐싱하지 못하게 막는다.
#### 6.3.2 Connection
- 전송하지 않을 ***헤더 필드를 지정하고 접속을 관리***
  - `Connection: 더 이상 전송하지 않는 헤더 (Hop-By-Hop)`
  - `Connection: Close or Keep-Alive`
#### 6.3.3 그 외 헤더들
- Date : HTTP 메시지를 생성한 날짜
- Pragma : 호환성을 위해 있는 헤더
- Trailer : 메시지 바디 뒤의 헤더 필드를 미리 전달
- Transfer-Encoding : 메시지 바디의 전송 코딩 형식을 지정
- Upgrade : 새로운 버전의 통신에 이용되는 경우에 사용
- Via : 클라이언트와 서버 간의 메시지의 경로를 전달
- Warning : 캐시에 관한 문제를 전달

### 6.4 리퀘스트 헤더 필드
- 요청에 사용되는 헤더로 `클라이언트의 정보`와 `컨텐츠의 우선 순위` 등을 추가한다.
#### 6.4.1 헤더들
  - Accept : 미디어 타입과 우선 순위을 전달 (Type : text, image, video, application)
  - Accept-Charset : 문자셋과 우선 순위를 전달
  - Accept-Encoding : 콘텐츠 코딩과 우선 순위를 전달 (Contents : gzip, compress, deflate, identity)
  - Accept-Language : 자연어의 세트와 우선 순위를 전달
  - Authorization : 인증 정보를 전달
  - Expect : 특정 동작을 요구를 전달
  - From : 메일 주소(보통 책임자)를 전달
  - Host : 리소스의 호스트와 포트 번호를 전달, ***유일한 필수 헤더 필드***
  - If-Match, If-Modified-Since, If-None-Match, If-Range, If-Unmodified-Since : 조건부 헤더
  - Max-Forwards : Trace 혹은 Options로 전송할 서버 최대치를 정
  - Proxy-Authorization : 프록시 서버에서 필요한 클라이언트의 정보를 전달
  - Range : 전달받을 리소스의 범위를 전달
  - Referer : 요청이 발생한 본래 리소스의 URI를 전달
  - TE : 응답으로 받을 수 있는 전송 코딩의 형식과 우선 순위를 전달
  - User-Agent : 요청을 생성한 브라우저와 유저의 정보를 전달

### 6.5 리스폰스 헤더 필드
- `서버의 정보`나 `클라이언트의 정보 요구` 등을 나타낸다.
#### 6.5.1 헤더들
- Accept-Ranges : Range 요청 접수 여부 (가능 : bytes, 불가능 : none)
- Age : 얼마나 오래 전에 생성되었는 지를 전달
- ETag : 엔티티 태그, 리소스를 특정하는 문자열을 전달
- Location : 요청 URI 이외의 리소스를 유도할 때 사용
- Proxy-Authenticate : 프록시 인증 요구를 전달
- Retry-After : 일정 시간 후 다시 요청하도록 전달 (Status : 503, 3xx)
- Server : HTTP 서버의 SoftWare를 전달
- Vary : 캐시를 컨드롤하기 위해서 사용
- WWW-Authenticate : HTTP 엑세스 인증에 사용

### 6.6 엔티티 헤더 필드
- 엔티티에 관한 정보를 포함한다. (ex. 컨텐츠의 갱신 시간 등)
#### 6.6.1 헤더들
- Allow : URI가 제공하는 메서드들을 전달
- Content-Encoding : 엔티티 바디에 적용된 컨텐츠 코딩 형식 전달
- Content-Language : 엔티티 바디에 적용된 자연어 전달
- Content-Length : 엔티티 바디의 크기(bytes) 전달
- Content-Location : 메시지 바디에 대응하는 URI 전달
- Content-MD5 : 메시지 바디가 잘 도착했는지 확인하는 값 전달 (MD5 알고리즘으로 검증)
- Content-Range : Range 요청에 대한 응답
- Content-Type : 엔티티 바디의 오브젝트의 미디어 타입 전달
- Expires : 리소스의 유효 기간 날짜를 전달
- Last-Modified : 마지막으로 갱신되었던 날짜 정보 전달

### 6.7 쿠키를 위한 헤더 필드
- 쿠키는 유저 식별과 상태 관리에 사용되는 기능이다.
- 적절하게 발행된다면 문제가 없겠지만 아니라면 외부의 공격에 데이터가 도난될 수 있다.
- 사양 : `넷스케이프`, `RFC2109`, `RFC2965`, `RFC6265` 넷 중 마지막 `RFC6265`만 쓰인다. 
  - Set-Cookie : 응답 헤더이다. 이름, 값, 만료일 등에 대한 데이터를 담아 보낸다.
  - Cookie : 요청 헤더이다. 발급받은 쿠키를 보낸다.

### 6.8 그 이외의 헤더 필드
- HTTP 헤더 필드는 ***독자적으로 확장할 수 있다***.
- X-frame-Option : 다른 웹 사이트의 프레임에서 표시를 제어하는 헤더이다. Click Jacking을 막는 것이 목적이다.
- X-XSS-Protection : 크로스 사이트 스크립팅(XSS)을 보호하는 응답 헤더이다.
- DNT : Do Not Track의 약어로 개인 정보 수집을 거부 의사를 나타내는 요청 헤더이다.

