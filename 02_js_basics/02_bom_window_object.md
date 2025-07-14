# 1. BOM (Browser Object Model)

-   브라우저와 JavaScript가 소통하도록 도와주는 객체 구조
-   가장 대표적인 객체: `window`

## 1-1. 주요 `window` 메서드

-   `window.alert('경고 메시지');`: 메시지 알림 창
-   `window.prompt('이름을 입력하세요');`: 사용자 입력 창
-   `window.confirm('확인하시겠습니까?');`: True/False 반환 다이얼로그
-   `window.console.log('hello world!');`: 콘솔창에 로그 메시지 출력

> 💡 `window.` → 생략 가능
>
> ```js
> window.alert('hi'); // → alert('hi')와 동일
> ```

> 💡 `window` 객체 탐색
>
> ```js
> // 다양한 브라우저 관련 기능과 속성을 확인 가능
> console.log(window);
> ```
