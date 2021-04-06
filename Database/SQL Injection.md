# SQL Injection
: 악의적인 사용자가 보안상의 취약점을 이용하여, 임의의 SQL문을 주입하고 실행되게 하여 데이터베이스가 비정상적인 동작을 하도록 조작하는 행위
<br />
## 공격 종류
### 1. Error based SQL Injection
- 논리적 에러를 이용한 방법
- 가장 많이 쓰임
- SELECT * FROM User WHERE id='input1' AND password='input2'
- (공격) input1<= ' OR 1=1--
- (결과) SELECT * FROM User WHERE id='<b>' OR 1=1--</b>' AND password='input2'
    - 일반적으로 로그인시 많이 사용되는 SQL문에 주입하여 가장 처음 만들어진 계정(보통 관리자계정)으로 로그인 되도록 한다. 
    - --뒤에는 주석처리

### 2. Union based SQL Injection
- Union 명령어를 이용한 방법
- 두가지 결과를 하나의 테이블로 보여주게 하는 키워드 
- 조건, Union하는 두 테이블의 컬럼수와 데이터 형이 같아야한다.

- SELECT * FROM Board WHERE title LIKE '%INPUT%' OR contents '%INPUT%'
- (공격) INPUT<= 'UNION SELECT null,id,passwd FROM User--

### 3. Blind SQL Injection
- Boolean based SQL
- 데이터베이스로부터 특정한 값이나 데이터를 전달받지 않고, 단순히 참과 거짓의 정보만 알 수 있을 때 사용
- 로그인 폼에 SQL Injection이 가능하다고 가정했을 때, 서버가 응답하는 로그인 성공과 로그인 실패 메시지를 이용하여, DB의 테이블 정보 등을 추출 할 수 있다.

<br />

## 대응방안
### 입력 값에 대한 검증
- 서버 단에서 화이트리스트 기반으로 검증 필요, 
	- 블랙리스트 기반으로 검증하게 되면 수많은 차단리스트를 등록해야하고, 하나라도 빠지면 공격에 성공하게 된다.
- 공백으로 치환하는 방법은 지양, 공백 대신 공격 키워드와는 의미 없는 단어로 치환 지향
### Prepared Statement 구문사용
- 사용자의 입력 값이 데이터베이스의 파라미터로 들어가기 전에 DBMS가 미리 컴파일 하여 실행하지 않고 대기
### Error Message 노출 금지
- 공격자에게 데이터베이스의 정보를 노출하지 않도록 주의
### 웹 방화벽 사용
