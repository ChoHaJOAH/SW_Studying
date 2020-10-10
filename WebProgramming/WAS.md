# WAS(Web Application Server)
### 클라이언트/서버 구조
- 서버: 서비스를 제공(웹 서버)
- 클라이언트: 서버에게 서비스를 요청하여 사용자에게 보여줌(웹 브라우저)

### DBMS (Database Management System)
- 데이터베이스를 관리하는 시스템, 다수의 사용자들이 데이터베이스 내의 데이터를 접근할 수 있도록 해주는 소프트웨어

### 미들웨어(MiddleWare)
- 클라이언트 쪽에 비즈니스 로직이 많을 경우, 클라이언트 관리(배포 등)로 인해 비용이 많이 발생하는 문제가 발생
- 비즈니스 로직을 클라이언트와 DBMS사이의 미들웨어 서버에서 동작하도록 함으로써 클라이언트는 입력과 출력만 담당하도록 함
- 클라이언트는 단순히 요청만 중앙에 있는 서버에 보내고, 미들웨어에서 대부분의 로직을 수행, 이때 데이터를 조작할 일이 있을때 DBMS에게 요청

### WAS(Web Application Server)
- 일종의 미들웨어로 웹 클라이언트(보통 웹 브라우저)의 요청 중 보통 웹 어플리케이션이 동작하도록 지원하는 목적을 가진다.
- Web Client---->Web Server(정적 컨텐츠)--->Web Application Server(동적 컨텐츠)
- 초기의 웹 브라우저는 정적 컨텐츠만 제공하였지만, 사용자의 요구가 늘어남에 따라 동적인 컨텐츠도 제공하게 되었다.
- 브라우저와 DBMS 사이에서 동작하는 미들웨어
- WAS의 기본기능
	- 프로그램 실행 환경과 데이터베이스 접속 기능을 제공
	- 여러 개의 트랜잭션(논리적인 작업단위) 관리
	- 업무를 처리하는 비즈니스 로직을 수행

### 웹 서버 vs WAS
- WAS도 보통 자체적으로 웹 서버 기능을 내장하고 있다.
- 현재는 WAS가 가지고 있는 웹 서버도 정적인 컨텐츠를 처리하는데 있어서 성능상 큰 차이가 있다.
- 규모가 커질수록 웹 서버와 WAS를 분리한다. 
- 웹 서버는 상대적으로 WAS보단 간단한 구조로 만들어져 있기 때문에 WAS앞단에 웹서버를 사용하기도 한다. 
	- 대용량 어플리케이션 같은 경우, 무중단으로 운영하기 위해 필요하기도 하다.(장애 극복 기능-failover)





참고: [부스트캠프](https://www.edwith.org/boostcourse-web/lecture/16666/)                                                                                     