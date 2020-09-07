# React vs Vue.js

### Vue 장점

- Template 과 Render Function 을 모두 사용할 수 있는 옵션
- 간편한 Syntax 와 프로젝트 설정
- 빠른 렌더링과 더 작은 용량

<br />

### React 장점

- 큰 규모에서 더 빛을 발하고, 테스팅 수월
- Web 과 Native 앱 개발에 모두 사용 가능
- 더 큰 개발자 생태계에서 오는 많은 레퍼런스와 도구들

<br />

### 공통된 장점

- View Layer 에 집중된 경량 UI 라이브러리
- 간단한 프로젝트부터 복잡한 프로젝트까지 사용 가능
- Virtual DOM 으로 빠른 렌더링
- 경량 라이브러리
- Reactive Component
- Server Side Rendering
- 라우터, 번들러, state management 와 결합이 쉬움
- 훌륭한 개발자 커뮤니티와 지원

<br />

## 차이점

- **<u>Vue</u>**
  1. **Templates 형식으로 앱 제작을 원한다면 Vue**
     - HTML 파일에 마크업을 작성하는 게 기본 설정
     - Angular와 비슷하게, 콧수염 괄호 `{{ }}` 로 데이터 바인딩
     - 표준 HTML 태그 이외에 Directive라는 특별 HTML Attribute를 활용해 Template의 기능 확장 가능
     - Template은 전통적인 웹 개발 패러다임과 유사해 입문 개발자가 이해하기 쉬움
     - Functionality 동작과 태그 Layout 을 분리할 수 있어 선호되는 방식
     - **단점**
       - Template 은 표준 HTML 이외에 추가적인 HTML 구문을 학습해야함
       - 버전 2.x부터 Template 과 render() 모두 지원
  2. **간단한 것과 '일단 동작' 되는 걸 좋아하면 Vue**
     - 별도의 변환작업 없이 브라우저에서 바로 동작
     - jQuery처럼 쉽게 프로젝트에 적용 가능
     - Vue 의 렌더링 과정
       - state 에 새로운 객체를 추가했을 때, Vue 가 해당 객체의 모든 속성을 확인하고 나서 getter 와 setter 로 변환
       - reactivity system이 모든 상태를 모니터링해 변경이 일어날 때마다 자동으로 DOM을 다시 렌더링
         - reactivity system 주의할 점
           - 속성 추가 및 삭제, 특정 배열에 대한 변경을 감지하지 못함
           - React 처럼 Vue set() API로 해결가능
       - 간단한 state 변경 + React보다 빠르고 효율적
  3. **빠르고 경량의 앱을 제작하고 싶다면 Vue**
     - Vue 의 렌더링 시스템이 React보다 빠름
- **<u>React</u>**
  1. **Template 구조를 사용하지 않고, 개발자가 JSX를 사용해 자바스크립트에서 DOM 생성**
     - **장점**
       - render() 는 표준 HTML 과 Javascript 만 알면 됨
       - render()를 활용해 쉽게 디버깅, 테스팅 가능
  2. **JSX 와 ES6에 의존함**
     - React에서 state 는 불변(immutable) 의 속성을 가짐, 직접적으로 변경 불가
     - 상태를 변경하고 싶다면 setState() 사용해야함
     - 현재와 이전 상태를 비교해 언제, 어떻게 다시 DOM 을 렌더링 할지 결정해야하므로 불변하는 속성 필요
  3. **Vue보다 많은 API 제공**
  4. **큰 규모의 앱을 만든다면, React**
     - Vue의 Template은 런타임 에러가 나오기 쉽고, 테스트하기가 어려우며 재구조화 하기 어려움
     - Javascript 으로 만들어진 React의 Template은 컴포넌트로 구성하기 쉽고, 재사용성이 높으며 테스트 하기가 용이
     - application data의 불변 속성이 복잡한 규모의 앱에서 테스트와 투명도 측면에서 장점을 가짐
     - 정밀한 렌더링 시스템이 구성 가능, shallow 렌더링 과 같은 기능들을 가짐
     - 테스팅 도구와 결합할 수 있어, 테스트하기 수월하고 더 유지보수 가능한 코드를 만들 수 있음
  5. **더 큰 개발 생태계를 원한다면 React**
     - React가 Vue보다 인기가 있었지만, 최근에는 Vue가 더 인기가 많아짐

<br />

### 예시) 프레임워크에서 데이터를 변경하는 방법이 다르다

- `fruit: "apple"` 라는 데이터가 있다고 가정

- <u>**Vue**</u>
  - `this.fruit`으로 값 호출
  - `this.fruit = "banana"`을 호출해 값 변경 가능
  - data를 업데이트 할 때마다 setState 알아서 수행

- <u>**React**</u>
  - `this.state.fruit`을 호출해 Vue.js처럼 같은 값 참조
  - But! 쉽게 값을 바꿀 수 없게 제약 걸려있음
  - `this.setState({fruit : "banana"})` 라고 작성해줘야함.
  - **this.setState**가 React의 state 변경을 돕는 도우미
    - setState가 필요한 이유?
      - React에서는 특정 라이프 사이클 훅(componentWillReceiveProps, shouldComponentUpdate, componentWillUpdate, render, componentDidUpdate)이 state를 변경할 때마다 다시 실행하려하기 때문
      - setState 함수를 호출하면 변경된 state를 알 수 있음
      - 만약 state를 직접적으로(Vue처럼) 바꾼다면, React에서는 변경을 감지하고 라이프 사이클 훅 실행 등을 위해 더 많은 작업을 해야함
      - 그래서 간단하게 하기 위해 setState 사용(권장 사항)

<br /><br />

#### 참고 링크

- https://medium.com/@erwinousy/%EB%82%9C-react%EC%99%80-vue%EC%97%90%EC%84%9C-%EC%99%84%EC%A0%84%ED%9E%88-%EA%B0%99%EC%9D%80-%EC%95%B1%EC%9D%84-%EB%A7%8C%EB%93%A4%EC%97%88%EB%8B%A4-%EC%9D%B4%EA%B2%83%EC%9D%80-%EA%B7%B8-%EC%B0%A8%EC%9D%B4%EC%A0%90%EC%9D%B4%EB%8B%A4-5cffcbfe287f
- https://joshua1988.github.io/web_dev/vue-or-react/
- 읽어보면 좋음 -> https://www.samsungsds.com/global/ko/support/insights/frameworks.html