# Oracle VS MySQL
## Oracle
: 성능이 좋고, 기능이 많지만 비싸다.
- 대규모 데이터베이스 지원
- 고성능 트랜잭션 처리 제공, 속도가 빠름
- SQL문을 실행하는 가장 효율적인 방법 선택
	- 비용을 최소화하기 위해 테이블과 인덱스 분석

<br />

## MySQL
: 오픈소스, 무료로 사용가능
- top n개의 레코드를 가지고 오는 케이스에 특화
- update 성능이 postgre보다 우수
- Nested Loop Join만 지원
> Nested Loop Join: 바깥 테이블의 처리 범위를 하나씩 접근하면서 추출된 값으로 안쪽 테이블을 조인하는 방식
> - 중첩 루프문과 동일한 원리
> - 좁은 범위에 유리
> - 순차적으로 처리
- 복잡한 알고리즘은 가급적 지원하지 않음
- 문자역 비교에서 대소문자를 구분하지 않음
- 간단한 처리 속도를 향상 시키는 것을 추구


### 여러 함수 비교
1. NULL 값 확인 함수 
```oracle
SELECT NVL(USER_ID,'') FROM USER
```
```MYSQL
SELECT IFNULL(USER_ID,'') FROM USER
```

2. 현재날짜 시간 확인
- oracle: SYSDATE
- MySQL: NOW()

3. 날짜포맷 변환 방법(date->String)
- oracle: TO_CHAR()
- MySQL: DATE_FORMAT()


참고: [Oracle, MySQL, PostgreSQL 차이점은?](https://velog.io/@jisoo1170/Oracle-MySQL-PostgreSQL-%EC%B0%A8%EC%9D%B4%EC%A0%90%EC%9D%80)
