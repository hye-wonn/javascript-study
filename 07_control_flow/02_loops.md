# 1. 반복문

-   특정 코드를 여러 번 반복 실행할 때 사용
-   코드의 효율성과 가독성 향상
-   **조건에 따라 반복하거나, 정해진 횟수만큼 반복** 가능

## 1-1. for문

-   정해진 횟수만큼 반복

```js
for (초기화식; 조건식; 증감식) {
    // 실행할 코드
}
```

```js
for (let i = 1; i <= 10; i++) {
    console.log(i);
}
```

> 💡 활용 1. 배열 요소 순회
>
> ```js
> const fruits = ['사과', '바나나', '포도'];
>
> for (let i = 0; i < fruits.length; i++) {
>     console.log(fruits[i]);
> }
> ```

> 💡 활용 2. HTMl 태그 조합
>
> ```js
> const cars = ['BMW', 'Volvo', 'Saab', 'Ford', 'Fiat', 'Audi'];
> let text = '';
>
> for (let i = 0; i < cars.length; i++) {
>     text += `<section><h2>${cars[i]}</h2></section>\n`;
> }
>
> console.log(text);
> ```

## 1-2. while문

-   조건이 `true`인 동안 반복
-   반복 횟수가 정해져 있지 않을 때 사용

```js
while (조건식) {
    // 실행할 코드
}
```

```js
let num = 0;
while (num <= 10) {
    console.log(num);
    num++;
}
```

## 1-3. `do...while` 문

-   **조건을 나중에 검사**하는 반복문
-   코드 블록을 **최소 한 번 실행한 후,** 조건이 참이면 계속 반복

```js
do {
    // 실행할 코드
} while (조건식);
```

```js
// 조건과 무관하게 최소 한 번 실행되는 특성 확인
let num = 5;

do {
    console.log('현재 숫자:', num);
    num++;
} while (num < 5); // 현재 숫자: 5
```

> 💡 추가 설명
>
> -   `while`문과의 차이점: **처음 실행할 때 조건 확인 X**
> -   최소 한 번은 실행해야 할 때 사용

## 1-4. 반복문 제어 (`break` & `continue`)

### 1-4-1. `break`

-   반복문 **즉시 종료**

```js
let num = 0;
while (num <= 10) {
    console.log(num);
    if (num === 5) {
        break;
    }
    num++;
}
```

### 1-4-2. `continue`

-   현재 반복만 **건너뛰고**, 다음 반복 진행

```js
for (let i = 0; i < 20; i++) {
    if (i < 13) {
        continue;
    }
    console.log(i + '살은 청소년입니다.');
}
```

## 1-5. `for...of` 문

-   배열, 문자열 등 반복 가능한 객체(iterable)를 순회할 때 사용
-   **요소의 값(value)**을 직접 가져와 인덱스가 필요 없는 경우에 유용
-   객체(Object)에는 사용 X (TypeError 발생)

```js
const colors = ['red', 'green', 'blue'];
for (const color of colors) {
    console.log(color);
}
```

## 1-6. `for...in` 문

-   객체의 **속성(key)**을 반복할 때 사용
-   변수에는 객체의 속성명이 할당되며, 해당 값을 가져오려면 [key] 사용
-   배열에도 사용할 수 있지만 권장 X (예상치 못한 속성까지 포함될 수 있음)

```js
const user = { name: '홍길동', age: 20, job: '개발자' };

for (let key in user) {
    console.log(`${key}: ${user[key]}`);
}
```
