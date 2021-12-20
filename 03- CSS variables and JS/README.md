# 02 Scoped CSS Variables and JS

<hr>

## 새로 알게된 것

- label 태그의 for속성: input태그를 제어하여 상태를 변경하게 도와주는 태그.
```html
<label for="spacing">Spacing</label>
<input id="spacing" type="range" name="spacing" min="10" max="200" value="10" data-sizing="px">
```
 <hr>
- document의 메소드인 querySelector는 Array가 아닌 NodeList 반환 -> foreach 사용 가능
  
```js
    const inputs = document.querySelectorAll('.controls input')
    inputs.forEach(input => input.addEventListener('change', handleUpdate)); // input값 바뀌면 handleUpdate 함수 호출
```
 <hr>
 

- DOM 트리 상단의 노드들은 document가 제공하는 프로퍼티를 사용해 접근할 수 있다.
  - ```<html>``` = ```document.documentElement```
  - ```<body>``` = ```document.body```
  <hr>
- js로 css제어하기 ```style.setProperty(propertyName, value, priority);```
```js
const suffix = this.dataset.sizing || '';
document.documentElement.style.setProperty(`--${this.name}`, this.value + suffix);
```