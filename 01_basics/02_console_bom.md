# 1. 콘솔 출력

## 1-1. 출력 기본: `console.log()`

```js
// 출력 결과는 브라우저 개발자 도구의 콘솔(Console) 탭에서 확인 가능
console.log('hello world!');
```

## 1-2. 콘솔 출력 관련 메서드

-   `console.log()`: 일반 메시지 출력
-   `console.error()`: 에러 메시지 출력
-   `console.warn()`: 경고 메시지 출력
-   `console.info()`: 정보 메시지 출력
-   `console.table()`: 데이터를 표 형태로 출력 (배열/객체에 유용)

# 2. BOM (Browser Object Model)

-   브라우저와 JavaScript가 소통하도록 도와주는 객체 구조
-   가장 대표적인 객체: `window`

## 2-1. 주요 `window` 메서드

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
