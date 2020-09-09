# DAO DTO VO

## DAO: Data Access Object

- DB를 사용해 데이터를 조회하거나 조작하는 기능을 전담하도록 만든 오브젝트, ConnectionPool 
- Mybatis는 커넥션풀까지 제공되고 있기 때문에 DAO를 별도로 만드는 경우가 드뭄
- Database에 접근을 하기위한 로직과 비즈니스 로직을 분리하기 위해서 사용
- DB에 대한 접근을 DAO가 담당하도록 하여 데이터베이스 엑세스를 DAO에서만 하게 되면 다수의 원격호출을 통한 오버헤드를 VO나 DTO를 통해 줄일 수 있고 다수의 DB 호출문제를 해결할 수 있습니다.

<br />

## DTO: Data Transfer Object

- 계층(Controller, View, Persistent 등)간 데이터 교환을 위한 자바빈즈
- 로직을 갖고 있지 않는 순수한 데이터 객체이며 속성과 그 속성에 접근하기 위한 getter, setter 메소드만 가진 클래스

<br />

## VO: Value Object

- 값 오브젝트로써 값을 위해 쓰인다.
- DTO와 다르게 read only 속성을 가짐, 중간에 값을 바꿀 수 없고, 새로 만들어야 한다는 특징이 있다.