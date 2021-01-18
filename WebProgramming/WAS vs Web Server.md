# WAS(Web Application Server) VS Web Server

## Static Pages와 Dynamic Pages

### Static Pages

- Web Server는 파일 경로 이름을 받아 경로와 일치하는 file contents를 반환
- 항상 동일한 페이지 반환
- ex) image, html, css, javascript 파일과 같이 컴퓨터에 저장되어 있는 파일들

### Dynamic Pages

- 인자의 내용에 맞게 동적인 contents 반환
- 웹 서버에 의해서 실행되는 프로그램을 통해서 만들어진 결과물
- 개발자는 Servlet에 doGet()구현
  - Servlet: WAS 위에서 돌아가는 Java Program

<br />

## Web Server와 WAS

### Web Server

- HW
  - web 서버가 설치되어 있는 컴퓨터
- SW
  - 웹 브라우저 클라이언트로부터 HTTP요청을 받아 정적인 컨텐츠(.html, .jpeg, .css 등)를 제공하는 컴퓨터 프로그램
- 기능
  - HTTP프로토콜을 기반으로 하여 클라이언트의 요청을 서비스 한다.
  - 기능1
    - 정적인 컨텐츠 제공
    - WAS를 거치지 않고 바로 자원을 제공
  - 기능 2
    - 동적인 컨텐츠 제공을 위한 요청 전달
    - 클라이언트의 요청을 WAS에 보내고, 그 결과를 클라이언트에게 전달한다.
- ex) Apache Server, Nginx, ISS(Windows 전용 Web 서버) 등

### WAS(Web Application Server)

- DB 조회나 다양한 로직 처리를 요구하는 동적인 컨테츠를 제공
- HTTP를 통해 컴퓨터나 장치에 애플리케이션을 수행해주는 미들웨어(소프트웨어 엔진)이다.
- 웹 컨테이너(Web Container), 서블릿 컨테이너(Servlet Container)라고도 불린다.
  - WAS는 jsp, Servlet 구동 환경을 제공한다.
- 역할
  - WAS = Web Server + Web Container
  - Web Server의 기능을 구조적으로 분리하여 처리하고자 하는 목적으로 제시
    - 분산 트랜잭션, 보안, 메시징, 스레드 처리 등의 기능을 처리하는 분산 환경에서 사용된다.
    - 주로 DB서버와 같이 수행된다.
  - 현재는 WAS가 가지고 있는 Web Server도 정적인 컨텐츠를 처리하는 데 있어서 성능상 큰 차이가 없다.
- 기능
  - 프로그램 실행 환경과 DB 접속 기능 제공
  - 여러개의 트랜잭션 관리 기능
  - 업무를 처리하는 비즈니스 로직 수행
- ex) Tomcat, JBoss, Jeus, Web Sphere 등









참고: [https://gmlwjd9405.github.io/2018/10/27/webserver-vs-was.html](https://gmlwjd9405.github.io/2018/10/27/webserver-vs-was.html)