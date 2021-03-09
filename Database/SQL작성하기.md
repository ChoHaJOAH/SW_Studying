# SQL 작성하기
## WHERE절
### index로 검색되지 않는 경우
- 변수앞에 '%'를 사용하는 경우
- IS NULL, IS NOT NULL을 사용한 비교
- 여러 칼럼에 대한 OR 조건 사용
	- 두 컬럼 모두 인덱스가 걸려있다고 하더라도, DBMS가 최적의 OR 조건을 뽑기 힘들어서 Full scan을 하는 경우가 많다.
- 부정형 비교
- 칼럼의 내외부 변형
#### index를 사용하지 않는 검색
```sql
SELECT * FROM ACCOUNT WHERE A_DAY+1>2;
SELECT * FROM ACCOUNT WHERE SUBSTR(A_STRDAY,1,1)='월';
SELECT * FROM EMP WHERE  EMP_ID = NVL(EMP_ID,'10');
```
#### index를 사용하는 검색
```sql
SELECT * FROM ACCOUNT WHERE A_STRDAY='월요일';

SELECT * FROM ACCOUNT WHERE A_DAY>2;

SELECT * FROM    EMP WHERE  EMP_ID = NVL('10','20');

SELECT * FROM ACCOUNT WHERE A_STRDAY like '월요일%';
```

### 성능 올리기 
- index를 타는 쿼리짜기
	- index를 사용하면 성능이 올라가지만 경우에 따라서는 테이블 전체를 검색하는 방법이 성능이 보장될 수도 있다.
- SELECT 쿼리문 작성시 필요한 칼럼만 명시, SELECT * 피하기
- WHERE 조건문의 왼쪽은 되도록 변형되지 않은 순수한 column만을 선언
	- AND를 사용할 경우 가장 왼쪽에서 대부분의 데이터가 걸러지도록 하기
- JOIN을 사용하는 경우 INNDER JOIN 사용
- 서브쿼리 사용시 불필요한 SELECT 구문을 줄이기


참고 : [https://link2me.tistory.com/544](https://link2me.tistory.com/544)
         [떳다떳다 블러그](https://starplaying.tistory.com/350)
