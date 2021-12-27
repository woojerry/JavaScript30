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

