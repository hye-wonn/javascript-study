# 1. 논리 자료형 (Boolean)

## 1-1. Boolean이란?

-   `true`, `false`만을 값으로 가지는 자료형
-   주로 **조건문**, **반복문**, **논리 판단** 등에 사용

## 1-2. 논리 연산자

### 1-2-1. 논리곱 (AND)

-   논리곱 연산자: `&&`
-   **모두 참**일 때만 `true`

```js
console.log(true && true); // true
console.log(true && false); // false
```

### 1-2-2. 논리합 (OR)

-   논리합 연산자: `||`
-   **둘 중 하나만 참\***이면 `true`

```js
console.log(true || false); // true
console.log(false || false); // false
```

### 1-2-3. 논리부정 (NOT)

-   논리부정 연산자: `!`
-   `true` → `false`, `false` → `true`로 반전

```js
console.log(!true); // false
console.log(!false); // true
```

## 1-3. Truthy & Falsy와 이중 부정 (`!!`)

### 1-3-1. Truthy & Falsy

-   Falsy: 조건문에서 `false`로 간주되는 값
-   Truthy: 그 외 모든 값

```js
// Falsy
false, 0, "", null, undefined, NaN

//Truthy
"hello", 1, [], {}, true, "0", "false" 등
```

### 1-3-2. 이중 부정

-   `!!`값 → 해당 값이 **truthy인지 falsy인지** 확인할 때 사용

```js
console.log(!!'hello'); // true (문자열은 truthy)
console.log(!!0); // false (숫자 0은 falsy)
console.log(!!undefined); // false
console.log(!!123); // true
```

## 1-4. `undefined`

-   **값을 할당하지 않은 변수**의 기본 값

```js
let userEmail;
console.log(userEmail); // undefined
```

## 1-5. `null`

-   **의도적으로 값이 없음을 지정할 때** 사용하는 값

```js
let userProfile = null;
console.log(userProfile); // null
```
