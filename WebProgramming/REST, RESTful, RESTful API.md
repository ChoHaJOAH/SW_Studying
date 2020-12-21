# REST, RESTful, RESTful API

### REST

- 분산 시스템 설계를 위한 <u>아키텍처 스타일</u>
  - 아키텍처 스타일 : <u>제약 조건</u>의 집합

<br />

### RESTful

- 제약 조건의 집합(아키텍처 스타일, 아키텍처 원칙)을 모두 만족하는 것

<br />

### API(Application Programming Interface)

- 응용 프로그램에서 사용할 수 있도록, 운영 체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스
- 소프트웨어가 다른 소프트웨어로부터 지정된 형식으로 요청, 명령을 받을 수 있는 수단

<br />

### REST API(REpresentational State Transfe API)

- 요청이 어떤 정보, 어떤 요청인지 요청의 모습으로 추론이 가능하다!!(RESTful한 API)
  - 보통 URI의 구성은 동사가 아닌 명사로 이루어져 있다.

#### Method

- POST, PUT, PATCH는 body를 가지고 있어서 GET, DELETE보다 많은 정보를 안전하게 보낼 수 있다.
- GET : read, 데이터 조회
- POST : create, 새로운 정보 추가
- PUT : update, 기존 정보를 변경
- PATCH : update, 기존 정보의 일부분을 특별한 방식으로 변경
- DELETE : delete, 기존 정보 삭제

<br />

### 정리

- **REST** : 아키텍처 스타일
- **RESTful API** : REST 아키텍처 원칙을 모두 만족하는 API
- REST와 RESTful은 엄격하게는 다르다



- 완벽한 REST는 WEB이다.
  - 어떤 Application이 생겼다고 브라우저는 버전을 업데이트할 필요가 없고,
    브라우저가 해당 application으로 어떻게 요청하는지를 알게 할 필요가 없기 때문이다
- RESTful API를 이용해 <u>하나의 큰 서비스 애플리케이션을 여러 모듈화된 작은 서비스 애플리케이션</u>(마이크로 서비스)들로 나눌 수 있다

<br /><br />

## REST가 필요한 이유

#### 1. 분산 시스템을 위해

- 거대한 애플리케이션을 모듈, 기능별로 분리하기 쉬워짐에 따라
  RESTful API를 서비스하기만 하면 어떤 다른 모듈 또는 애플리케이션들이라도 RESTful API를 통해 상호간에 통신을 할 수 있다

#### 2. WEB브라우저 외의 클라이언트를 위해 (멀티 플랫폼)

- 웹 페이지를 위한 HTML 및 이미지등을 보내던 것과 달리
  데이터만 보내면 여러 클라이언트에서 해당 데이터를 적절히 보여주면 된다
- 서버는 요청한 데이터만 보내주면되기 때문에 가벼워지고 유지보수성도 좋아졌다
- ex) 모바일 애플리케이션으로 <u>html</u> 같은 파일을 보내는 것은 무겁고 브라우저가 모든 앱에 있는 것은 아니기 때문에 부적합,
        <u>RESTful API</u>를 사용하면 데이터만 주고 받기 때문에 여러 클라이언트가 자유롭게 데이터를 이용할 수 있다

<br />

## REST의 구성 요소

- HTTP URI : 자원

- HTTP Method : 행위

- MIME Type : 표현 방식

- ex) 아래의 <u>**Request**</u>를 보냈을 경우,

  - ```http
    GET /100 HTTP/1.1
    Host : aaa.com
    ```

  - HTTP URI : **/100**

  - HTTP Method : **GET**

  - MIME Type : 보통 Response Http header 메세지에 **Content-type**으로 쓰임(예시의 경우 없음)

  - => aaa.com 서버에 /100 이라는 자원을 GET(조회)하고 싶다는 요청 

  

  - 아래의 **<u>Response</u>**가 돌아왔을 때, 

  - ```http
    HTTP/1.1 200 OK
    Content-Type : application/json-patch+json
     
    [{"title": "test_title", "author": "test"}]
    ```

  - **Content-Type** : application/json-patch+json

    - Body의 내용이 json타입이라는 것을 알 수 있음

<br />

## REST의 제약 조건

1. Client/Server

2. Stateless : 각 요청에 클라이언트의 context가 서버에 저장되어서는 안된다.

3. Cacheable : 클라이언트는 응답을 캐싱할 수 있어야 한다.

4. Layered System : 클라이언트는 서버에 직접 연결되었는지 미들웨어에 연결되었는지 알 필요가 없어야 한다.

5. Code on demand(option) : 서버에서 코드를 클라이언트에게 보내서 실행하게 할 수 있어야 한다.

6. **uniform interface** 

   - 자원은 유일하게 식별가능해야한다.

   - HTTP Method로 표현을 담아야한다.

   - ** 메세지는 스스로를 설명(**self-descriptive**)해야한다.

   - ** 하이퍼링크를 통해서 애플리케이션의 상태가 전이(**HATEOAS**)되어야 한다.

     - ```http
       HTTP/1.1 200 OK
       Content-Type : application/json
       Link : </spring/1>; rel="previous",
               </spring/3>; rel="next";
       {
           "title" : "spring의 모든 것"
           "author" : "jeong-pro"
       }
       ```

     - HTTP 헤더 중 **Link**에 다른 리소스를 가리켜 주는 값을 넣어 HATEOAS를 해결한다.

     - 위와 같이 해당 정보에서 다른 정보로 넘어갈 수 있는 하이퍼링크를 명시한다.



- 1~5번의 제약 조건은 HTTP를 기반으로하는 REST는 HTTP에서 이미 충분히 지켜지고 있는 부분
- RESTful하려면 6번 제약 조건인 **uniform interface**, 그중에서도 **self-descriptive**와 **HATEOAS**를 잘 지켜야 한다.
  - Spring은 두 제약을 지키기위해 사용할 수 있는 라이브러리인 
    *spring-data-rest, spring hateoas, spring-rest-doc*가 있다.

<br />

## 장단점

### 장점

- 메세지를 단순하게 표현할 수 있고 WEB의 원칙인 확장에 유연 (멀티플랫폼)
- 별도의 장비나 프로토콜이 필요없이 기존의 HTTP 인프라를 이용 가능 (사용이 용이함)
- server, client를 완전히 독립적으로 구현 가능



### 단점

- 표준, 스키마가 없어 API 문서가 필요
- 행위에 대한 메소드가 제한적 (GET, POST, PUT, DELETE, HEAD, ...)

<br />

## cf) URI와 URL의 차이점

- **URI** : Uniform Resource <u>Identifier</u>

- **URL** : Uniform Resource <u>Locator</u>
- URI는 URL보다 큰 개념이다.
- REST에서는 모든 것을 유일한 것을 나타내는 Resource(즉, Identifier, 식별자)로 표현한다. 
  - URI는 파일뿐만 아니라 여러 자원들 까지도 포함하는 개념이다.
    따라서 URL은 URI의 부분집합이다.
- 과거의 웹은 html 같은 파일들을 주고 받았기 때문에 Identifier의 개념이 따로 필요없었다.
  따라서 파일의 위치를 가리키는 Locator를 사용했다.

<br /><br />

#### 참고

- https://jeong-pro.tistory.com/180?category=793347

- REST 가이드라인
  - https://github.com/Microsoft/api-guidelines/blob/vNext/Guidelines.md