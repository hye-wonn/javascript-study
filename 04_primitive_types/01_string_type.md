# 1. 문자열 (String)

## 1-1. 문자열이란?

-   작은따옴표, 큰따옴표, 백틱으로 감싸서 표현
-   **인덱스(0부터 시작)**를 가짐
-   **수정 불가능(immutable)**하며, 변경 시 새로운 문자열 생성

## 1-2. 문자열 인덱싱 & 길이

### 1-2-1. 인덱싱

```js
let text = 'javascript';

console.log(text[0]); // 'j'
console.log(text[4]); // 's'
```

### 1-2-2. 길이 확인

```js
let password = 'pass123!';
console.log(password.length); // 8
```

## 1-3. 문자열의 불변성

-   문자열의 개별 문자 직접 수정 불가

```js
let word = 'hello';

// word[0] = 'H'; → 불가능
let newWord = word.toUpperCase();

console.log(newWord); // 'HELLO'
console.log(word); // 여전히 'hello'
```

## 1-4. 문자열 주요 메서드

### 1-4-1. `indexOf()`

-   특정 문자의 **첫 번째 인덱스** 반환

```js
'Hello'.indexOf('e'); // 1
```

### 1-4-2. `includes()`

-   특정 문자열 포함 여부 반환 (`true` / `false`)

```js
'Hi there'.includes('there'); // true
```

### 1-4-3. `replace()`

-   특정 문자 또는 문자열을 다른 문자로 교체

```js
'abc'.replace('a', 'z'); /// 'zbc'
```

### 1-4-4. `slice(start, end)`

-   문자열의 일부를 잘라내어 반환 (`start` ~ `end - 1`)

```js
let word = 'javascript';
console.log(word.slice(0, 4)); // 'java'
console.log(word.slice(-3)); // 'ipt'
```

### 1-4-5. `split('구분자')`

-   구분자를 기준으로 문자열을 나누어 배열로 반환

```js
'a,b,c'.split(','); // ['a','b','c']
```

### 1-4-6. `toLowerCase()` / `toUpperCase()`

-   문자열 전체를 소문자 / 대문자로 변환

```js
'HELLO'.toLowerCase() // 'hello'
'hello'.toUpperCase() → 'HELLO'
```

### 1-4-7. `trim()`

-   문자열 앞뒤의 공백 제거

```js
' hi '.trim(); // 'hi'
```

## 1-5. 문자열 연결 & 템플릿 리터럴

### 1-5-1. 문자열 연결

-   `+` 연산자 사용

```js
let first = 'Good';
let second = 'Morning';

console.log(first + ' ' + second); // 'Good Morning'
```

### 1-5-2. 템플릿 리터럴 (Template Literals)

-   백틱으로 문자열 작성
-   `${변수명}` 또는 `${표현식}`을 사용해 문자열 내에 변수나 값 삽입 가능

```js
let name = 'hye won';
let age = 20;

console.log(`My name is ${name} and I am ${age} years old.`);
// 결과: My name is hye won and I am 20 years old.
```

```js
let x = 5;
let y = 3;

console.log(`5 + 3 = ${x + y}`); // '5 + 3 = 8'
```
