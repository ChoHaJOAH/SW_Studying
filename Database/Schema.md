# 데이터베이스 구조(Schema)

- 논리적 구조: 사용자 관점에서 본 구조, 사용자가 이해하고 생각하는 것을 나타내는 형태
- 물리적 구조: 저장 장치(기계) 관점에서 본 구조, 기계 처리에 맞는 형태

### 스키마(Schema)

- 데이터베이스의 전체적인 구조와 제약조건에 대한 명세를 기술, 정의한 것
- [사용자] <====> [외부 스키마] <====> [개념 스키마] <====> [내부 스키마] <====> (저장 DB)
- 내부 스키마(Internal Schema): 기계 관점의 물리적 구조
- 개념 스키마(Conceptual Schema): 사용자 관점의 전체적인 데이터 구조
- 외부 스키마(External Schema): 전체 데이터 중 사용자가 사용하는 한 부분에서 본 논리적 구조, 서브 스키마

### 데이터베이스 관리자(Database Administrator, DBA)

- 데이터베이스 시스템과 관련된 모든 자원에 대해 기획, 통제하며, 데이터베이스 언어를 이용해 DBMS를 거쳐 DB의 전체적인 관리 운영에 책임을 지는 집단

#### 역할

- 데이터베이스 구성요소 결정
- 저장 구조와 접근 방법 설정
- 보안, 권한 부여, 유효성 검사 등을 수행
- 스키마를 정의
- 예방, 회복 절차 수립 등을 모색
- 무결성 유지를 위한 관리

-  유지 시킵니다.