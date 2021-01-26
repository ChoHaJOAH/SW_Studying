# Lombok, 롬복

- 자바 개발할 때 자주 사용하는 코드 Getter, Setter, 기본생성자, toString 등을 어노테이션으로 자동 생성해주는 자바 라이브러리
- 이클립스는 롬복 설치가 번거롭고, 인텔리제이에선 플러그인 덕분에 쉽게 설정 가능

## 설치하기

- build.gradle에 코드 추가

```
compile('org.projectlombok:lombok')
```

- 롬복 플러그인 설치
- 인텔리제이 다시 시작

## 실제 사용하기

```java
@Getter
@Setter
@RequiredArgsConstructor
public class MyDto{
    private final String name;
    private final int id;
}
```

- Getter
  - 선언된 모든 필드의 get메소드를 생성
- Setter
  - 선언된 모든 필드의 set메소드를 생성
- RequiredArgsConstructor
  - 선언된 모든 final 필드가 포함된 생성자를 생성
  - final이 없는 필드는 생성자에 포함되지 않는다.