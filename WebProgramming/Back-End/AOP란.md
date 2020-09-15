# AOP(Aspect Oriented Programming)

: 관점지향 프로그래밍

- 핵심 기능과 공통 기능을 분리시켜놓고, 공통 기능을 필요로 하는 핵심 기능들에서 사용하는 방식(핵심 기능은 변화하지만, 공통 기능은 다시 적용이 가능하다.)

ex)

```java
class A{
    int a = 10;
    //여기에 어떤 일을 하는 코드 A가 있다.---->1
    a++;
    //여기에 어떤 일을 하는 코드 B가 있다.---->2
} 

class B{
    int a = 10;
    //여기에 어떤 일을 하는 코드 A가 있다.---->1
    a--;
    //여기에 어떤 일을 하는 코드 B가 있다.---->2
}
```

- 1, 2와 같이 각기 다른 class에 같은 일을 하는 코드가 있다면 A와 B를 변경해야 할때, 4줄의 코드를 바꿔야 하기 때문에 이것은 관점지향 프로그래밍이라고 할 수 없다. 

### AOP의 방법

1. 컴파일 단계에서 처리

   .java-----(AOP)----->.class : AspectJ가 제공하는 기능

2. .class 파일이 메모리에 로드되기 전 로더가 처리 

   .class-----(AOP)----->메모리 : AspectJ가 제공하는 기능

3. Proxy pattern 이용 -----> Spring의 방법



### 주요용어

- Aspect: 공통기능
- Advice: Aspect의 기능 자체
- Jointpoint: Advice를 적용해야 되는 부분(ex: 필드, 메소드)
- Pointcut: Jointpoint의 부분으로 실제로 Advice가 적용된 부분
- Weaving: Advice를 핵심기능에 적용하는 행위



### "스프링에서 AOP 구현방법: proxy를 이용한다."

