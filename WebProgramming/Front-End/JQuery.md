# JQuery
## .attr()와 .prop()의 차이, 1.6버전  기준
### .attr()
- element 속성값을 반환하는 함수
```javascript
//속성값 반환
$("태그").attr("속성")

//속성관 변환
$("태그").attr("속성", "새로운 값")
```
### .prop()
- element 상태값(ex. 체크여부 등)을 반환하는 함수
```javascrpit
$("태그").prop('checked') //false/true
//.attr로 한다면 처음 상태만 계속 반환할 것...
```

## .bind() vs .on()
- 같은 일을 수행하고 사용형식도 같으나 1.7버전 이후로 나온것이 on!
