# 01 JS Drum kit

<hr>

## 새로 알게된 것 
-  ```<link>``` 태그의 rel 속성은 ```<link>``` 요소에 반드시 명시되어야 하는 필수 속성 현재 문서와 외부 리소스 사이의 연관 관계를 명시
-  ```<kbd>``` 키보드 입력, 음성 입력 등 임의의 장치를 사용한 사용자의 입력을 나타낸다.
- ```<html>```은 모든 엘리먼트들 중에서 최상위 단계 Global Style은 항상 ```<html>```에 사용해야 하는 것이 아니다. HTML 레퍼런스에 따르면
    - ```background, background-color, margin, font``` 는 ```<body>```에 선언해줄 것을 명시하고 있다.

- JS로 class 조작하기
  ```js
  const key = document.querySelector(`.key[data-key='${e.keyCode}']`)
  key.classList.add('playing'); // playing이라는 이름의 클래스 추가
  ```

- ```transitionend``` Event: transition이 완료된 이후에 발생하는 이벤트, transition 완료를 감지
   ```js
    const keys = document.querySelectorAll('.key');
    keys.forEach(key => key.addEventListener('transitionend', removeTransition));
    // 모든 key들 중 각각 transitionend 이벤트가 감지되면 removeTransition 함수 실행
   ```