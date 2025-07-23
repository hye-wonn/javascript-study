# 1. 함수 활용

## 1-1. 함수 표현식

-   익명 함수를 변수에 할당하는 방식
-   선언 이후에만 호출 가능 (Hoisting X)

```js
const add = function (x, y) {
    return x + y;
};

console.log(add(2, 3)); // 5
```

## 1-2. 화살표 함수

-   간결한 함수 표현식
-   선언 이후에만 호출 가능 (Hoisting X)

```js
const multiply = (a, b) => a * b;

console.log(multiply(3, 4)); // 12
```

> 💡 추가 설명
>
> -   매개변수 하나일 때 괄호 생략 가능
> -   본문이 여러 줄일 경우 중괄호와 `return` 명시 필요
>
> ```js
> const divide = (a, b) => {
>     if (b === 0) return null;
>     return a / b;
> };
> ```

## 1-3. 콜백 함수

-   다른 함수의 인자로 전달되어 나중에 실행되는 함수
-   비동기 처리, 이벤트, 배열 메서드 등에 자주 사용

```js
function greetUser(name, callback) {
    console.log(`Hello, ${name}!`);
    callback();
}

greetUser('Alice', () => {
    console.log('Goodbye!');
});
```

> 💡 설명
>
> 1. `greetUser`는 두 개의 매개변수 `name`과 `callback`을 받는 함수
>    함수 안에서 `Hello, Alice!`를 출력한 뒤, `callback()` 호출
>    이때 콜백으로 넘긴 `() => { console.log('Goodbye!'); }` 실행

## 1-4. 즉시 실행 함수

-   선언과 동시에 실행되는 함수
-   변수 범위(scope) 분리, 모듈 패턴 등에 활용

```js
(function () {
    console.log('즉시 실행');
})();
```

## 1-5. 재귀 함수

-   자기 자신을 호출하는 함수
-   반복 작업을 함수로 표현할 때 유용

```js
function factorial(n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1);
}

console.log(factorial(5)); // 120
```

## 1-6. 함수 호이스팅 (Hoisting)

| 함수 선언 방식 | 호이스팅 여부           |
| -------------- | ----------------------- |
| 함수 선언문    | 선언 이전에도 호출 가능 |
| 함수 표현식    | 선언 이후에만 호출 가능 |
| 화살표 함수    | 선언 이후에만 호출 가능 |

```js
// 함수 선언문
console.log(dec()); // 3

function dec() {
    return 3;
}
```

```js
// 함수 표현식
console.log(exp); // undefined
// console.log(bar()); → ReferenceError

const exp = function () {
    return 5;
};
```
