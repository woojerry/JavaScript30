## 새로 알게된 것 & 복습

### JS array 관련 메소드

#### filter
> 배열의 모든 요소들을 돌면서 전달한 콜백함수의 인자로 넣고 호출한다.콜백 함수의 반환된 값이 ```true```인 요소들을 모아 새로운 배열을 만들어서 리턴한다.

```js
const fifteen = inventors.filter(inventor =>
(inventor.year >= 1500 && inventor < 1600
))
```

#### map
> 배열의 모든 요소들을 돌면서 전달한 콜백함수의 인자로 넣고 호출한다. 콜백함수의 반환된 값들을 모두 요소로 담아서 새로운 배열을 리턴한다.
```js
const fullnames = inventors.map((inventor) => `${inventor.first} ${inventor.last}`)
```

#### sort
> 배열을 정렬한다.
- sortFunction 인수에 함수를 지정하면 아래의 값 중 하나가 반환
  - 첫 번째 인수가 두 번째 인수보다 작을 경우 - 값
  - 두 인수가 같을 경우 0
  - 첫 번째 인수가 두 번째 인수보다 클 경우 + 값
```js
onst arr = [5, 3, 2, 4, 6, 1];
const res;

res = arr.sort(); // sort((a, b) => a - b)과 동일
```
```js
// 오름차순
const ordered = inventors.sort((a, b) => a.year - b.year)
//   const ordered = inventors.sort((a, b) => a.year > b.year ? 1 : -1);
```
```js
const oldest = inventors.sort(function (a, b) {
    const lastInventor = a.passed - a.year;
    const nextInventor = b.passed - b.year;
    return lastInventor > nextInventor ? -1 : 1;
})
```
#### reduce 
> 원하는 시작점부터 모든 배열의 요소들을 돌면서 어떤 값을 누적할 때 사용한다.(앞 요소부터)
```js
const totalYears = inventors.reduce((total, inventor) => {
    return total + (inventor.passed - inventor.year);
}, 0);
```

## Array로 만들기
```js
const category = document.querySelector('.mw-category');
// Array.from 쓰기
const links = Array.from(category.querySelectorAll('a'));
```
```js
// spread parameter 쓰기
const links = [...category.querySelectorAll('a')];
```