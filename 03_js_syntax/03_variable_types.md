# 1. 변수 타입

## 1-1. 원시 타입

-   값 자체를 복사하여 저장
-   변경 불가능(immutable)

| 타입      | 설명                |
| --------- | ------------------- |
| Boolean   | `true` 또는 `false` |
| Number    | 정수 및 실수        |
| String    | 텍스트              |
| Null      | `null` (값이 없음)  |
| Undefined | 값이 할당되지 않음  |
| Symbol    | 고유한 식별자       |
| BigInt    | 큰 정수 (`123n`)    |

### 1-1-1. 원시 타입 예시

```js
let isRaining = true;
let temperature = 25;
let city = 'Jeju';
let nothing = null;
let notDefined;
let uniqueId = Symbol('id');
let bigNum = 12345678901234567890n;
```

## 1-2. 참조 타입

-   메모리 주소를 참조하여 저장

| 타입                 | 설명                               |
| -------------------- | ---------------------------------- |
| Object (객체)        | 키-값 쌍으로 구성된 데이터         |
| Array (배열)         | 여러 값을 순서대로 저장하는 리스트 |
| Function (함수)      | 실행 가능한 코드 블록              |
| Date (날짜)          | 날짜 및 시간 관련 객체             |
| RegExp (정규 표현식) | 정규 표현식 객체                   |

### 1-2-1. 참조 타입 예시

```js
// Object
let user = { name: 'hye won' };

// Array
let arr = [1, 2, 3];

// Function
let f = function () {};

// Date
let today = new Date();

// RegExp
let r = /abc/;
```

## 1-3. 변수 타입 확인 방법

### 1-3-1. `typeof`

-   원시 타입 및 함수 타입 확인

```js
typeof 123; // "number"
typeof 'hi'; // "string"
typeof null; // "object" (버그)
typeof []; // "object"
typeof function () {}; // "function"
```

> 💡 `typeof`는 **배열**과 **객체**를 모두 "object"로 반환

### 1-3-2. `instanceof`

-   참조 타입 생성자 확인

```js
[] instanceof Array;             // true
{} instanceof Object;            // true
new Date() instanceof Date;      // true
function(){} instanceof Function // true
```

> 💡 `instanceof`는 참조 타입(객체)을 정확히 구별 가능

## 1-4. 변수 저장 방식

### 1-4-1. 원시 타입

```js
let a = 5;
let b = a;
a = 10;

console.log(a); // 10
console.log(b); // 5 (값 복사 → a를 변경해도 영향 X)
```

### 1-4-2. 참조 타입

```js
let obj1 = { name: 'Lee' };
let obj2 = obj1;

obj2.name = 'Park';

console.log(obj1.name); // 'Bob' (동일 객체 참조)
console.log(obj2.name); // 'Bob'
```
