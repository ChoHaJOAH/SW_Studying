# Scope(스코프, 유효범위) 

- 참조 대상 식별자(identifier, 변수, 함수의 이름과 같이 어떤 대상을 다른 대상과 구분하여 식별할 수 있는 유일한 이름)를 찾아내기 위한 규칙

- 모든 변수는 스코프를 갖는다.
  - 전역스코프(Global scope) : 코드 어디에서든지 참조 가능
  - 지역스코프(Local scope) : 지역과 하부 지역에서만 참조 가능

#### var - function-scope

- 함수안에서는 다 사용 가능하다.(함수 안에 있는 if문에서 선언한 것도 사용 가능)
- 재선언 가능

#### let, const - block-scope

- 블록안에서만 사용 가능하다.
- 재선언 불가능
- const  - 재할당 불가능
