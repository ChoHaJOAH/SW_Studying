# JPA(Java Persistence API)

- 자바 표준 ORM(Object Relational Mapping), 인터페이스

#### ORM

: 서로 지향하는 바가 다른 2개 영역(객체지향 프로그래밍 언어와 관계형 데이터베이스)을 중간에서 패러다임 일치를 시켜주기 위한 기술

- 패러다임 불일치
  - 관계형 데이터베이스: 어떻게 데이터를 저장할지에 초점이 맞춰진 기술, 객체지향 프로그래밍 언어: 기능과 속성을 한 곳에서 관리하는 기술, 이 둘의 패러다임이 서로 다른데, 객체를 데이터베이스에 저장하려 할 때 문제가 발생한다.

#### JPA

- 개발자는 객체지향적으로 프로그래밍을 하고 JPA가 이를 관계형 데이터베이스에 맞게 SQL을 대신 생성해서 실행
- 개발자는 항상 객체지향적으로 코드를 표현할 수 있으니 더는 SQL에 종속적인 개발을 하지 않아도 된다.



### Spring Data JPA

- 인터페이스인 JPA를 사용하기 위해서는 구현체가 필요하다. 
  - 대표적으로 Hibernate, Eclipse Link등
- spring에서 JPA를 사용할 때는 이 구현체들을 직접 다루지 않고, Spring Data JPA라는 모듈을 이용하여 JPA를 다룬다.
- JPA <-- Hibernate <-- Spring Data JPA
- why?
  - 구현체 교체의 용이성
    - Hibernate외에 다른 구현체로 쉽게 교체하기 위함
    - Spring Data JPA 내부에서 구현체 매핑을 지원
  - 저장소 교체의 용이성
    - 관계형 데이터베이스 외에 다른 저장소로 쉽게 교체하기 위함
    - MongoDB로 교체가 필요하다면 개발자는 Spring Data JPA에서 Spring Data MongoDB로 의존성만 교체하면 된다.
    - Spring Data의 하위 프로젝트 들은 기본적인 CRUD의 인터페이스가 같다.



## 어노테이션

```java
@Entity
public class Posts {
    @Id
    @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    
    @Column(length = 500, nullable = false)
    private String title;
    
    @Column(columnDefinition = "TEXT", nullable = false)
    private String content;
    
    private String author;
    
    @Builder
    public Posts(String title, String content, String author){
        this.title = title;
        this.content = content;
        this.author = author;
    }
}
```

@Entity

- 테이블과 링크될 클래스임을 나타낸다.
- 기본값으로 클래스의 카멜케이스 이름을 언더스코어 네이밍으로 테이블 이름을 매칭
  - SalesManager.java->sales_manager table

@Id

- 해당 테이블의 PK필드를 나타낸다.

@GeneratedValue

- PK의 생성 귳칙

@Column

- 테이블의 칼럼, 굳이 선언하지 않더라도 해당 클래스의 필드는 모두 칼럼이 된다.
- 기본값 외에 추가로 변경이 필요한 옵션이 있으면 사용