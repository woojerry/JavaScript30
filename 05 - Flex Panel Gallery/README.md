## 새로 알게된 것

### JS toggle()
> ```add(), remove()```가 합쳐진 개념으로 on/off 가능
```js
function toggleOpen() {
            this.classList.toggle('open')
        } // open class를 껐다켰다 가능
```        

### CSS 전이 이벤트
```transitionend```: CSS 전이가 완료되었을 때
```js
function toggleActive(e) {
    if (e.propertyName.includes('flex')) {
        this.classList.toggle('open-active')
    }
}

panels.forEach(panel => panel.addEventListener('transitionend', toggleActive))
```

### Flex 축약형
- flex 축약형의 값은 flex-grow, flex-shrink, flex-basis 순서로 지정됨
- ```flex-grow```: 주축에서 남는 공간을 항목들에게 분배하는 방법을 결정
- ```flex-shrink```: 주축의 공간이 부족할때 각 항목의 사이즈를 줄이는 방법을 정의
- ```flex-basis```: flex 항목이 넓어지거나 좁아질 때 고려하는 기준 값
  <hr>
-  ```flex: 1;``` 이런 식으로 flex-basis를 생략해서 쓰면 flex-basis의 값은 0이 된다.
-  ```flex-shrink```를 **0으로 세팅하면** 아이템의 크기가 flex-basis보다 작아지지 않기 때문에 **고정폭의** 컬럼을 쉽게 만들 수 있다.
-  ```flex-basis```의 기본값 auto는 해당 아이템의 width값을 사용. width를 따로 설정하지 않으면 컨텐츠의 크기
```css
item {
	flex: 1;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 0%; */
	flex: 1 1 auto;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: auto; */
	flex: 1 500px;
	/* flex-grow: 1; flex-shrink: 1; flex-basis: 500px; */
}
```
```css
flex: 1 0 auto;
```