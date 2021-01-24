# Call by Reference vs Call by Value

- 평가 전략(Evaluation Strategy)
  - 프로그래밍 언어에서 함수 호출의 아규먼트의 순서를 언제 결정하고 함수에 어떤 종류의 값을 통과시킬지 결정하는 것

## Call by Reference

: 매개 변수의 원래 주소(값에 대한 참조 주소, 메모리 주소를 담고 있는 변수)에 값을 저장하는 방식

- 클래스 객체를 인수로 전달한 경우

## Call by Value

: 주어진 값을 복사하여 처리하는 방식

- 인수로 기본 데이터형을 사용
- 메서드 내의 처리 결과는 메서드 밖의 변수에 영향을 미치지 않는다.



<추가>

## Call by Sharing

- 자바스크립트에서는 call by reference는 존재하지 않고 call by value만 존재한다.

- 참조 타입을 인자로 넘기면 참조값에 대한 복사본이 넘어간다.

  

