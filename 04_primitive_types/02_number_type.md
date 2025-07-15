# 1. 숫자형 (Number)

## 1-1. 숫자형 특징과 연산자

### 1-1-1. 산술 연산

-   산술 연산자: `+`, `-`, `*`, `**` (거듭제곱), `/`, `%` (나머지)

```js
console.log(`5 + 2 = ${5 + 2}`); // 7
console.log(`5 - 2 = ${5 - 2}`); // 3
console.log(`5 * 2 = ${5 * 2}`); // 10
console.log(`5 / 2 = ${5 / 2}`); // 2.5
console.log(`5 % 2 = ${5 % 2}`); // 1
console.log(`5 ** 2 = ${5 ** 2}`); // 25
```

### 1-1-2. 단항 연산

-   `+`: 양수 유지
-   `-`: 부호 반전

```js
console.log(-10); // -10
console.log(+10); // 10
console.log(-(-10)); // 10
```

### 1-1-3. 증감 연산자

-   `++`(증가), `--`(감소)
-   위치에 따라 연산 순서 결정

```js
let count = 1;

console.log(++count); // 2 (먼저 증가 후 출력)
console.log(count++); // 2 (출력 후 증가 → count = 3)
console.log(--count); // 2 (먼저 감소 후 출력)
console.log(count--); // 2 (출력 후 감소 → count = 1)
```

### 1-1-4. 비교 연산자 (`true` / `false`)

-   `>`, `>=`, `<`, `<=`, `==`, `===`, `!==`

```js
console.log(5 > 3); // true
console.log(5 >= 5); // true
console.log(2 < 1); // false
console.log(2 <= 2); // true

console.log(2 == '2'); // true (값만 비교)
console.log(2 === '2'); // false (값과 타입 모두 비교)

console.log(2 != '2'); // false
console.log(2 !== '2'); // true
```

### 1-1-5. 특수 숫자 값

```js
console.log(1 / 0); // Infinity
console.log(-1 / 0); // -Infinity
console.log('hello' / 2); // NaN (숫자가 아님)

console.log(5e3); // 5000 (지수 표현식: 5 * 10^3)
console.log(9e1000); // Infinity (숫자 범위 초과)
```

### 1-1-6. BigInt (큰 정수 표현)

-   숫자 뒤에 `n`을 붙여 사용하며, 정수만 표현 가능

```js
let normalNumber = 1234567890123456789;
console.log(normalNumber); // 정밀도 손실 발생 가능

let bigIntNumber = 1234567890123456789n;
console.log(bigIntNumber); // BigInt로 정확히 표현 가능

console.log(bigIntNumber + 1n); // 1234567890123456790n
// console.log(bigIntNumber + 1); → TypeError (다른 타입과 연산 불가)
```

## 1-2. 숫자형 관련 함수 및 메서드

-   문자열을 정수(`parseInt`) 또는 실수(`parseFloat`)로 변환
-   `parseInt(문자열, 진수)`로 진수 변환 가능

### 1-2-1. `parseInt()` & `parseFloat()`

```js
console.log(parseInt('42')); // 42
console.log(parseFloat('3.14')); // 3.14
console.log(parseInt('99.99')); // 99
console.log(parseInt('abc')); // NaN
console.log(parseInt('20px')); // 20

console.log(parseInt('1010', 2)); // 10 (2진수 → 10진수)
console.log(parseInt('17', 8)); // 15 (8진수 → 10진수)
```

### 1-2-2. `toString()`

-   숫자를 문자열로 변환하거나, 진수 표현으로 변환

```js
let num = 10;

console.log(num.toString()); // '10'
console.log((10).toString(2)); // '1010' (2진수)
console.log((10).toString(16)); // 'a' (16진수)
```

> 💡 10.toString(2)는 문법 오류이므로 (10).toString(2)처럼 괄호로 감싸야 함

### 1-2-3. `isNaN()` vs `Number.isNaN()`

-   `isNaN()`: 값을 숫자로 변환 가능한지 확인

-   `Number.isNaN()`: 정확히 NaN인지 확인

```js
console.log(isNaN('100')); // false (변환 가능)
console.log(isNaN('hi')); // true (변환 불가)
console.log(isNaN(undefined)); // true

console.log(Number.isNaN('hi')); // false (문자열 자체는 NaN 아님)
console.log(Number.isNaN(NaN)); // true
console.log(Number.isNaN(undefined)); // false
```

### 1-2-4. `Math` 내장 객체

-   수학 관련 다양한 기능 제공

```js
console.log(Math.PI); // 3.141592...

console.log(Math.round(4.6)); // 5 (반올림)
console.log(Math.floor(4.9)); // 4 (내림)
console.log(Math.ceil(4.1)); // 5 (올림)

console.log(Math.abs(-7)); // 7 (절대값)
console.log(Math.pow(2, 3)); // 8 (2^3)
console.log(Math.sqrt(9)); // 3 (제곱근)

console.log(Math.max(3, 7, 1)); // 7 (최댓값)
console.log(Math.min(3, 7, 1)); // 1 (최솟값)
```
