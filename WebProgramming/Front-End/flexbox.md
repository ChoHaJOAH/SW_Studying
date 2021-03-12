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
### 속성
#### 부모요소 속성
- 전체적인 정렬이나 흐름에 관련된 속성
- flex-direction, flex-wrap, justify-content, align-items, align-content
#### 자식요소 속성
- 요소의 크기나 순서에 관련된 속성
- flex, flex-grow, flex-shrink, flex-basis, order




참고: [flexbox로 만들 수 있는 10가지 레이아웃](https://d2.naver.com/helloworld/8540176)
