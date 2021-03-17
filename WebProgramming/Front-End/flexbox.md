# flexbox
- 뷰포트나 요소의 크기가 불명확하거나 동적으로 변할 때에도 효율적으로 요소를 배치, 정렬, 분산할 수 있는 방법을 제공하는 CSS3의 새로운 레이아웃방식
- 복잡한 계산없이 요소의 크기와 순서를 유연하게 배치할 수 있다.
## flexbox의 구성
- flex item, flex container
![](https://d2.naver.com/content/images/2018/12/helloworld-201811-flex_01.png)
```html
.flex_container {
	display: flex;
}
```
- display: flex; 속성이 적용된 요소가 flex container, 그 자식 요소가 flex item
- 주축(main axis)을 기준으로 정렬되고, 기본은 row이다. 
	- 왼쪽->오른쪽
## 속성
### 부모요소 속성
- 전체적인 정렬이나 흐름에 관련된 속성
#### display
: Flex Container를 정의
	- flex: Block특성의 Flex Container를 정의, 수직 쌓임
	- inline-flex: Inline 특성의 Flex Container를 정의, 수평 쌓임
	- 두 값의 차이는 내부 Items에는 영향을 주지 않고, Container간의 관계

#### flex-flow
``` css
.flex-container {
	flex-flow: row-reverse wrap;
}
```
: flex-direction와 flex-wrap의 단축 속성
	- flex-direction: Flex Items의 주 축(<->교차축)을 설정
		- row / row-reverse / column / column-reverse
	- flex-wrap: Items의 여러 줄 묶음 설정
		- nowrap / wrap / wrap-reverse

#### justify-content
: 주 축의 정렬 방법을 설정
	- flex-start:	Items를 시작점(flex-start)으로 정렬
	- flex-end	:	Items를 끝점(flex-end)으로 정렬
	- center:		Items를 가운데 정렬
	- space-between:	시작 Item은 시작점에, 마지막 Item은 끝점에 정렬되고 나머지 Items는 사이에 고르게 정렬됨
	- space-around:	Items를 균등한 여백을 포함하여 정렬

### 자식요소 속성
- 요소의 크기나 순서에 관련된 속성
- flex, flex-grow, flex-shrink, flex-basis, order




참고: 
[flexbox로 만들 수 있는 10가지 레이아웃](https://d2.naver.com/helloworld/8540176)
[CSS Flex(Flexible Box)완벽 가이드](https://heropy.blog/2018/11/24/css-flexible-box/)

