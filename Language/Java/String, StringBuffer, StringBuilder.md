# String, StringBuffer, StringBuilder

## String

- 불변의 속성
  - +를 사용하여 문자열을 늘릴경우, 기존의 값이 변하는 것이 아닌 새로운 값이 생성되고, 이전 값은 GC의 대상이 된다.

```java
String str = new String("hello");
//str ->hello
str = str+"world";
//str ->helloworld      hello->GC의 대상
```

- 계속해서 한 변수에 문자열을 변경한다면 힙 메모리에 많은 가비지가 생성된다.
- 현재 자바에선 한줄짜리 문자열 +연산은 StringBuilder를 사용해 수정해주지만 반복문안에서 사용한다면 StringBuilder도 계속 해서 생성되므로 효율적이지 않다.

## StringBuffer, StringBuilder

- 가변성
- 동일 객체내에서 문자열을 변경할 수 있다.

### StringBuffer vs StringBuilder

- 동기화 유무의 차이
  - StringBuffer는 동기화 키워드를 지원하여 멀티스레드 환경에서 안전(String도 멀티스레드 환경에서 안전하다)
  - StringBuilder는 동기화를 지원하지 않지만, 단일쓰레드에서의 성능은 StringBuffer보다 뛰어나다.