## 새로 알게된 것

### JS array 관련 메소드 2

#### some
> ```some()``` 메서드는 배열 안의 **어떤 요소라도** 주어진 판별 함수를 통과하는지 테스트한다.
```js
const people = [
    { name: 'Wes', year: 1988 },
    { name: 'Kait', year: 1986 },
    { name: 'Irv', year: 1970 },
    { name: 'Lux', year: 2015 }
];
```
```js
const idAdult = people.some(person => {
const currentYear = (new Date()).getFullYear();
return currentYear - person.year >= 19
})
// 한명이라도 19세이상인 사람이 있으므로 true를 반환
```

#### every
> ```every()``` 메서드는 배열 안의 **모든** 요소가 주어진 판별 함수를 통과하는지 테스트

```js
const allAdults = people.every(person => ((new Date()).getFullYear()) - person.year >= 19);
// 모든 사람이 19세이상이 아니므로 false를 반환
```


#### find
> ```find()``` 메서드는 주어진 판별 함수를 만족하는 첫 번째 요소의 **값**을 반환
```js
const comment = comments.find(comment => comment.id === 823423);
```

#### findIndex
> ```findIndex()``` 메서드는 주어진 판별 함수를 만족하는 배열의 첫 번째 요소에 대한 **인덱스**를 반환
```js
const index = comments.findIndex(comment => comment.id === 823423);
```