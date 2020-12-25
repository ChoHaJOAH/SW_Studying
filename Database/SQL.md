# SQL(Structured Query Language)

- 데이터베이스에서 데이터를 정의, 조작, 제어하기 위해 사용하는 언어
- 관계 대수와 관계 해석을 기초로 데이터베이스의 작업을 보다 효율적이고, 다양하게 표현하고 처리하기 위한 고급 데이터베이스 언어

### DDL(Data Definition Language): 데이터베이스나 테이블 등을 생성, 삭제, 변경하는 명령어

- ex) CREATE, ALTER, DROP

- ```sql
  CREATE TABLE 테이블_이름
  	({속성_이름 데이터_타입 [NOT NULL],}
      [PRIMARY KEY(속성_이름),]
      [UNIQUE(속성_이름),]
      [FOREIGN KEY(속성_이름) REFERENCES 참조테이블(속성_이름)]
       [ON DELETE CASCADE | SET NULL | SET DEFAULT | NO ACTION]
       [ON UPDATE CASCADE | SET NULL | SET DEFAULT | NO ACTION],
      [CONSTRAINT 제약조건_이름 CHECK(속성_이름=범위 값)]
      );
  ```

### DML(Data Manipulation Language): 데이터베이스에 저장된 데이터를 처리, 조회, 검색하는 명령어

- ex) INSERT, UPDATE, DELETE, SELECT 등

### DCL(Data Control Language): 데이터베이스에 저장된 데이터를 관리하기 위해 보안성 및 무결성 등을 제어하기 위한 명령어

- ex) GRANT, REVOKE 등

<br />

#### 생각해보기!

- sql문이 실행되는 순서를 알고 있나요?

  - select쿼리문을 실행했을 때 처리 순서는 FROM - WHERE - GROUP BY - HAVING - SELECT - ORDER BY순입니다.

  