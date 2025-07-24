# 1. 전개 구문

-   배열이나 객체를 복사하거나 병합하는 데 사용

## 1-1. 배열 전개 구문

-   대괄호 `[]` 안에서 `...`를 사용하여 전개

### 1-1-1. 배열 병합

```js
const fruits = ['사과', '배'];
const vegetables = ['당근', '오이'];

const food = [...fruits, ...vegetables];
console.log(food); // ['사과', '배', '당근', '오이']
```

### 1-1-2. 배열 복사

```js
const fruits = ['딸기', '포도'];
const copied = [...fruits];

copied.push('망고');

console.log(fruits); // ['딸기', '포도']
console.log(copied); // ['딸기', '포도', '망고']
```

## 1-2. 객체 전개 구문

-   `...`를 사용하여 전개
-   같은 키가 있을 경우 뒤에 오는 객체가 값을 덮어씀

### 1-2-1. 객체 병합

```js
const userInfo = { name: '홍길동', age: 20 };
const userContact = { email: 'hong@example.com', phone: '010-1234-5678' };

const user = { ...userInfo, ...userContact };
console.log(user);
// { name: '홍길동', age: 20, email: 'hong@example.com', phone: '010-1234-5678' }
```

### 1-2-2. 객체 복사

```js
const settings = { darkMode: true, fontSize: '16px' };
const copiedSettings = { ...settings };

copiedSettings.darkMode = false;

console.log(settings.darkMode); // true
console.log(copiedSettings.darkMode); // false
```

# 2. 디스트럭처링 (Destructuring)

## 2-1. 객체 디스트럭처링

-   객체에서 속성을 꺼내 변수에 직접 할당
-   객체의 키와 변수명이 일치해야 함
-   필요한 값만 뽑아 사용할 수 있어 코드가 간결함

### 2-1-1. 기본 객체 디스트럭처링

```js
const person = { name: '이순신', age: 45, job: '장군' };

const { name, age } = person;
console.log(name); // '이순신'
console.log(age); // 45
```

### 2-1-2. 함수 반환값 디스트럭처링

```js
function getUser() {
    return {
        id: 1,
        username: 'user1',
        email: 'user1@example.com',
    };
}

const { username, email } = getUser();
console.log(username); // 'user1'
console.log(email); // 'user1@example.com'
```

### 2-1-3. 다른 변수명으로 할당

```js
const user = { id: 123, nickname: '홍삼이' };

const { nickname: name } = user;
console.log(name); // '홍삼이'
```

## 2-2. 배열 디스트럭처링

-   배열 순서에 따라 각 요소를 변수에 할당
-   나머지 요소를 `...` 전개 구문으로 추출 가능

### 2-2-1. 기본 배열 디스트럭처링

```js
const colors = ['빨강', '파랑', '초록'];

const [first, second, third] = colors;
console.log(first); // '빨강'
console.log(second); // '파랑'
console.log(third); // '초록'
```

### 2-2-2. 일부만 할당

```js
const numbers = [10, 20, 30];

const [a, , c] = numbers;
console.log(a); // 10
console.log(c); // 30
```

### 2-2-3. 나머지 요소 받기

```js
const fruits = ['사과', '배', '수박', '포도'];

const [first, ...rest] = fruits;
console.log(first); // '사과'
console.log(rest); // ['배', '수박', '포도']
```

## 2-3. 중첩 구조 디스트럭처링

-   중첩된 객체나 배열 내부에 접근할 때도 디스트럭처링 가능
-   코드 간결성, 가독성, 유지보수 효율성 향상

```js
// 객체의 중첩 구조 디스트럭처링
const user = {
    name: '이몽룡',
    address: {
        city: '남원',
        zip: '12345',
    },
};

const {
    address: { city },
} = user;

console.log(city); // '남원'
```

```js
// 배열의 중첩 구조 디스트럭처링
const arr = [1, [2, 3], 4];

const [a, [b, c], d] = arr;

console.log(a); // 1
console.log(b); // 2
console.log(c); // 3
console.log(d); // 4
```

## 2-4. 디스트럭처링 기본값

-   디스트럭처링 시 해당 값이 `undefined`일 경우 사용할 기본값을 설정 가능
-   객체, 배열 모두 기본값 지정 가능
-   예외 처리, 초기값 설정 등에 유용

```js
// 객체 디스트럭처링 기본값
const { title = '제목 없음' } = {};
console.log(title); // '제목 없음'
```

```js
// 배열 디스트럭처링 기본값
const [a = 1, b = 2] = [10];
console.log(a); // 10
console.log(b); // 2
```

# 3. 전개 구문 + 디스트럭처링

-   객체나 배열을 복사하면서 필요한 값만 뽑아낼 때 매우 유용
-   흔히 React나 Vue 등에서 props 처리 시 자주 사용

```js
// 디스트럭처링과 나머지 객체
const user = {
    name: '김자바',
    age: 25,
    country: 'Korea',
    job: 'developer',
};

const { name, ...rest } = user;

console.log(name); // '김코딩'
console.log(rest); // { age: 25, country: 'Korea', job: 'developer' }
```

> 💡 추가 설명
>
> -   Vue: 프론트엔드 개발에 사용되는 자바스크립트 프레임워크
> -   props: 상위 컴포넌트가 하위 컴포넌트에 데이터를 전달할 때 사용하는 속성
