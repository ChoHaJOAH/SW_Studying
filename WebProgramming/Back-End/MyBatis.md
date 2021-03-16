# MyBatis
- 자바의 관계형 데이터 베이스 프로그래밍을 좀 더 쉽게 개발 할 수 있게 도와주는 프레임워크
- 이전에 자바는 jdbc api를 사용하여 개발했는데, 이는 코드 안에 SQL문법이 들어가 있어서 재사용성등이 안좋아지는 단점이 있다.
### 특징
- 한 두줄의 자바 코드로 DB 연동을 처리
- SQL 명령어를 자바 코드에서 분리하여 XML 파일에 따로 관리
#### IBatis는 아파치에 있을때, 구글로 넘어가면서 Mybatis로 이름이 바뀜

## MyBatis API
- SqlSessionFactoryBuilder 클래스
	- build() 메소드를 통해 mybatis-config를 로딩하여 SqlSessionFactory 객체를 생성
- SqlSessionFactory 클래스 
	- SqlSession객체에 대한 팩토리 객체
	- openSession()이라는 메소드로 객체를 얻을 수 있다.
- SqlSession 클래스
	- Mapper XML에 등록된 SQL을 싱행하기 위해 API를 제공



