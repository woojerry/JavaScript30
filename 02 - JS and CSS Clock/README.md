# 02 JS + CSS Clock

<hr>
## 새로 알게된 것
 
- ```transform-origin```은 CSS transform 속성과 함께 사용되는 속성으로서, 회전 **중심**(원점·기준점)을 지정
    ```css
    // default 50%
    // right -100%
    transform-origin: 100%;
    ```

- ```setInterval(func, delay)``` 일정 시간 간격을 두고 함수를 실행
    ```js
    function setDate() {
        const now = new Date();
        const seconds = now.getSeconds();
        const secondsDegrees = (seconds / 60) * 360 + 90;
        secondHand.style.transform = `rotate(${secondsDegrees}deg`;

        const mins = now.getMinutes();
        const minDegrees = (mins / 60) * 360 + 90;
        minsHand.style.transform = `rotate(${minDegrees}deg`

        const hour = now.getHours();
        const hourDegrees = (hour / 12) * 360 + 90;
        hourHand.style.transform = `rotate(${hourDegrees}deg`

    }

    setInterval(setDate, 1000);
    ```