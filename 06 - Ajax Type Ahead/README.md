## 새로 알게된 것

### Spread operator
- spread operator ```...```는 배열의 원소들을 쪼개어 각각의 개별요소를 반환
```js
fetch(endpoint)
    .then(blob => blob.json())
    // spread operator(...)은 배열의 원소들을 쪼개어 각각의 개별요소를 반환
    .then(data => cities.push(...data))
```

### innerHTML
> QuerySelector로 가져온 도큐먼트 오브젝트의 내용이나, 내부 HTML 코드를 JavaScript 코드에서 변경할 수 있다.

```js
function displayMatches() {
            const matchArray = findMatches(this.value, cities);
            const html = matchArray.map(place => {
                const regex = new RegExp(this.value, 'gi');
                const cityName = place.city.replace(regex, `<span class="hl">${this.value}</span>`);
                const stateName = place.state.replace(regex, `<span class="hl">${this.value}</span>`);
                return `
                    <li>
                        <span class='name'>${cityName}, ${stateName}</span>
                        <span class='population'>${numberWithCommas(place.population)}</span>
                    </li>
                    `;
            }).join('');
            // Array.join() 
            // join() 메서드는 배열의 모든 요소를 연결해 하나의 문자열로 만든다.
            suggestions.innerHTML = html;

        }
const searchInput = document.querySelector('.search');
const suggestions = document.querySelector('.suggestions');

searchInput.addEventListener('change', displayMatches)
```