# 1. 조건문

-   프로그램 흐름 제어를 위해 사용
-   특정 조건이 참인지 거짓인지에 따라 실행되는 코드가 변함

```js
let 초록불 = true;

if (초록불) {
    console.log('횡단보도를 건넙니다.');
} else {
    console.log('기다립니다.');
}
```

## 1-1. `if`문

### 1-1-1. 기본 구조

-   `true` → 해당 블록의 코드 실행
-   `false` → 아무 것도 실행 X

```js
let num = 5;
if (num < 10) {
    console.log('num은 10보다 작습니다.');
}
```

> 💡 추가 설명 및 주의 사항
>
> -   조건문 안의 코드가 **한 줄**일 경우, 중괄호 `{}` 생략 가능
> -   **가독성을 위해 생략하지 않는 것을 권장**
>
> ```js
> if (true) console.log('중괄호를 생략했습니다.');
> ```

### 1-1-2. `if-else` 문

-   조건이 **참일 때와 거짓일 때 각각 다른 로직 실행**
-   `true` → 해당 블록 실행
-   `false` → `else` 블록 실행

```js
let x = 3;
let y = 7;

if (x === y) {
    console.log('x와 y가 같습니다.');
} else {
    console.log('x와 y가 다릅니다.');
}
```

### 1-1-3. `if - else if - else` 문

-   여러 개의 조건을 순차적으로 검사할 때 사용
-   **첫 번째로 참인 조건이 실행**되고 이후 조건은 검사 X

```js
let score = 76;
let grade;

if (score > 90) {
    grade = 'A';
} else if (score > 80) {
    grade = 'B';
} else if (score > 70) {
    grade = 'C';
} else if (score > 60) {
    grade = 'D';
} else {
    grade = 'F';
}

console.log(`당신의 학점은 ${grade}입니다.`);
```

## 1-2. `switch`문

-   하나의 변수 또는 표현식을 여러 값과 비교할 때 사용
-   각 `case`는 비교할 값을 의미하며, 해당 값이 일치하면 코드 실행

```js
// 기본 구조
switch (표현식) {
    case 값1:
        // 실행 코드
        break;
    case 값2:
        // 실행 코드
        break;
    default:
        // 기본 실행 코드
        break;
}
```

```js
let day = new Date().getDay();

switch (day) {
    case 1:
        console.log('월요일입니다.');
        break;
    case 2:
        console.log('화요일입니다.');
        break;
    case 3:
        console.log('수요일입니다.');
        break;
    case 4:
        console.log('목요일입니다.');
        break;
    case 5:
        console.log('금요일입니다.');
        break;
    default:
        console.log('주말입니다.');
        break;
}
```

### 1-2-1. `break`

-   `case` 실행 후 `switch`문을 빠져나오게 하는 역할
-   `break` 생략 시 다음 `case` 연속 실행 (의도된 경우 제외하고 반드시 사용)

```js
let menu = '카페라떼';
let price = 0;

switch (menu) {
    case '아메리카노':
        price = 4000;
        break;
    case '카페라떼':
        price = 5000;
        break;
    case '바닐라라떼':
        price = 6000;
        break;
    default:
        console.log('메뉴를 다시 확인해주세요.');
}

console.log(`가격은 ${price}원입니다.`);
```

### 1-2-2. `default`

-   모든 `case`에 해당하지 않을 때 실행
-   생략 가능하지만 보통 에러 처리 또는 예외 메시지 출력을 위해 사용

```js
let menu = '딸기스무디';

switch (menu) {
    case '아메리카노':
        console.log('아메리카노를 주문했습니다!');
        break;
    case '카페라떼':
        console.log('카페라떼를 주문했습니다!');
        break;
    default:
        console.log('없는 메뉴입니다. 다시 확인해주세요.');
}
```

## 1-3. 삼항 연산자 (`조건식 ? 참 : 거짓`)

-   간단한 조건문일 경우 `if` 대신 사용 가능

```js
let age = 20;
let message = age >= 18 ? '성인입니다.' : '미성년자입니다.';
console.log(message);
```
