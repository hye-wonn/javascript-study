# 1. 함수 (Function)

## 1-1. 함수란?

-   특정 작업을 수행하는 코드 블록
-   반복되는 코드를 줄이고 **재사용성**, **유지보수성**, **가독성** 향상

## 1-2. 함수 선언

-   `function` 키워드를 사용하여 정의

```js
function 함수이름(파라미터) {
    // 실행할 코드
    return 결과값;
}
```

## 1-3. 함수 호출

-   함수 이름과 괄호()를 사용해 호출
-   괄호 안에는 **전달인자(Argument)** 입력

```js
function greet(name) {
    return `Hello, ${name}!`;
}

console.log(greet('Alice')); // Hello, Alice!
```

## 1-4. 매개변수(Parameter)와 전달인자(Argument)

### 1-4-1. Parameter vs Argument

| 용어      | 의미                          |
| --------- | ----------------------------- |
| Parameter | 함수 선언 시 정의하는 변수    |
| Argument  | 함수 호출 시 전달하는 실제 값 |

```js
// a, b: 파라미터
function add(a, b) {
    return a + b;
}

console.log(add(3, 5)); // 3, 5: 아규먼트 → 8
```

### 1-4-2. 파라미터 개수 불일치

-   전달인자가 부족하면 undefined, 많으면 무시

```js
function info(name, age) {
    console.log(name, age);
}

info('Tom'); // Tom undefined
info('Tom', 20, 'extra'); // Tom 20 (세 번째는 무시됨)
```

### 1-4-3. 기본값 파라미터

-   파라미터에 기본값을 지정 가능

```js
function greet(name = 'Guest') {
    console.log(`Hello, ${name}`);
}

greet(); // Hello, Guest
greet('Alice'); // Hello, Alice
```

### 1-4-4. 나머지 파라미터

-   `...`을 사용해 여러 개의 인자를 배열로 받음

```js
function concatenate(separator, ...words) {
    return words.join(separator);
}

console.log(concatenate(' - ', 'apple', 'banana', 'cherry'));
// apple - banana - cherry
```

## 1-5. 함수의 반환값

### 1-5-1. 반환값이 있는 함수

-   `return` 키워드를 사용해 값 반환
-   `return`을 만나면 함수 즉시 종료

```js
function multiply(x, y) {
    return x * y;
}

let result = multiply(4, 5);
console.log(result); // 20
```

### 1-5-2. 반환값이 없는 함수

-   `return`이 없거나 반환값이 명시되지 않으면 `undefined` 반환

```js
function sayHello() {
    console.log('Hello!');
}

let msg = sayHello(); // 함수는 실행되지만 반환값 없음
console.log(msg); // undefined
```
