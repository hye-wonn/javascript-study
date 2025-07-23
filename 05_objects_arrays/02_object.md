# 1. 객체

## 1-1. 객체의 특징

-   여러 값을 키(key)와 값(value) 쌍으로 저장할 수 있는 자료형
-   키를 통해 값에 접근
-   키와 값의 쌍 → 속성

> 💡 속성 값이 함수 → 메소드(method)

```js
const person = {
    name: 'Alice',
    age: 25,
    job: 'Engineer',
};
```

### 1-1-1. 객체 생성

-   중괄호 `{}`를 사용하여 생성

```js
const car = {
    brand: 'Tesla',
    model: 'Model S',
    start() {
        console.log('Car is starting...');
    },
};
```

### 1-1-2. 객체 속성 접근

-   점 연산자(`.`) / 대괄호 연산자 (`[]`) 사용

```js
console.log(car.brand); // Tesla
console.log(car['model']); // Model S
```

> 💡 대괄호 연산자 → 속성명이 변수명 규칙을 따르지 않은 경우에 사용

### 1-1-3. 객체 속성 추가 및 삭제

-   `객체_이름.새로운_속성_이름 = 값`: 속성 추가
-   `delete`: 속성 제거

```js
car.color = 'Red'; // 속성 추가
delete car.model; // 속성 삭제
console.log(car);
```

### 1-1-4. 객체 속성 확인

-   `in`: 특정 키가 객체에 있는지 확인

```js
console.log('brand' in car); // true
console.log('owner' in car); // false
```

### 1-1-5. 중첩 객체

-   계층적 구조 표현에 유용

```js
const user = {
    name: 'Bob',
    contact: {
        email: 'bob@example.com',
        phone: '123-456-7890',
    },
};

console.log(user.contact.email); // bob@example.com
```

### 1-1-6. 객체 반복 (`for...in` 루프)

-   **열거 가능한 속성**을 순회할 때 사용
-   각 키에 접근하며, 값은 `객체[key]` 형식으로 접근

```js
for (let key in car) {
    console.log(`${key}: ${car[key]}`);
}
```

### 1-1-7. 객체 복사

-   객체 직접 할당: 참조값 복사 → 복사본 수정 시 원본도 함께 변경
-   얕은 복사: **1단계 속성만 복사** (중첩된 객체는 여전히 참조 복사)
-   깊은 복사: 중첩된 모든 객체를 **재귀적으로 복사** → 원본과 완전히 독립적인 복사본

```js
// 직접 복사
const original = { x: 10, y: 20 };
const copy = original; // 참조값 복사

copy.x = 99;
console.log(original.x); // 99 → original도 변경됨

// 얕은 복사
// 방법 1. Object.assign() 함수 사용
const original = { x: 10, y: 20 };
const copy = Object.assign({}, original);
copy.x = 99;

console.log(original.x); // 10 (원본 변경 X)

// 방법 2. 전개 연산자 (...) 사용
const copy2 = { ...original };
copy2.x = 99;

console.log(original.x); // 10

// 깊은 복사
// 방법 1. structuredClone() (최신 브라우저/환경 지원)
const original = { a: 1, b: { c: 2 } };
const deepCopy = structuredClone(original);

deepCopy.b.c = 99;
console.log(original.b.c); // 2 (원본 영향 X)

// 방법 2. SON 방식
// 단점: 함수, undefined, 순환 참조 → 처리 불가
const deepCopy2 = JSON.parse(JSON.stringify(original));
deepCopy2.b.c = 99;

console.log(original.b.c); // 2
```

## 1-2. 객체의 주요 메서드

### 1-2-1. `Object.keys(obj)`

-   키만 배열로 반환

```js
const fruits = { a: 'Apple', b: 'Banana', c: 'Cherry' };
console.log(Object.keys(fruits)); // ['a', 'b', 'c']
```

### 1-2-2. `Object.values(obj)`

-   값만 배열로 반환

```js
console.log(Object.values(fruits)); // ['Apple', 'Banana', 'Cherry']
```

### 1-2-3. `Object.entries(obj)`

-   [키, 값] 쌍을 배열로 묶어 2차원 배열 형태로 반환

```js
console.log(Object.entries(fruits));
// [['a', 'Apple'], ['b', 'Banana'], ['c', 'Cherry']]
```
