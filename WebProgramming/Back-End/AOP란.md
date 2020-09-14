# AOP(Aspect Oriented Programming)

: 관점지향 프로그래밍

- 핵심 기능과 공통 기능을 분리시켜놓고, 공통 기능을 필요로 하는 핵심 기능들에서 사용하는 방식(핵심 기능은 변화하지만, 공통 기능은 다시 적용이 가능하다.)

### 주요용어

- Aspect: 공통기능
- Advice: Aspect의 기능 자체
- Jointpoint: Advice를 적용해야 되는 부분(ex: 필드, 메소드)
- Pointcut: Jointpoint의 부분으로 실제로 Advice가 적용된 부분
- Weaving: Advice를 핵심기능에 적용하는 행위



### "스프링에서 AOP 구현방법: proxy를 이용한다."

ㄴ