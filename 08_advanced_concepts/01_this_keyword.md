# 1. `this`

## 1-1. 전역 컨텍스트 (Global Context)

-   브라우저 환경: `window` 객체 참조
-   strict mode (`use strict`): `undefined`

```js
console.log(this); // window 객체 출력 (브라우저)

('use strict');
console.log(this); // undefined (strict mode)
```

## 1-2. 함수 호출

-   일반 함수: 전역 객체(`window`) 참조
-   strict mode: `undefined`

```js
// 일반 함수
function showThis() {
    console.log(this);
}

showThis(); // window
```

```js
// strict mode
'use strict';
function showThisStrict() {
    console.log(this);
}

showThisStrict(); // undefined
```

## 1-3. 메서드 호출

-   객체의 메서드로 호출된 함수: 메서드를 소유한 **객체** 참조

```js
const obj = {
    name: 'licat',

    // sayName: obj 객체의 메서드(함수형 속성)
    sayName: function () {
        // 이 함수가 호출될 때, this는 이 메서드를 소유한 obj 객체를 참조함
        console.log(this.name);
    },
};

obj.sayName(); // 'licat'
```

## 1-4. 화살표 함수

-   화살표 함수는 `this`를 자체적으로 가지지 않음
-   상위 스코프(lexical scope)의 `this`를 그대로 사용

```js
const obj = {
    name: 'licat',
    sayName: () => {
        // sayName이 정의된 위치: 'obj = { ... }'라는 객체 리터럴 내부
        // JS에서 객체 리터럴 내부 → this를 결정하는 특별한 범위 X

        // 따라서 상위 스코프인 전역(Global) 영역의 this를 그대로 가져옴
        // 전역 this (브라우저) → window 객체 참조

        // this.name → window.name
        // window.name 따로 지정 X → undefined 출력
        console.log(this.name);
    },
};

obj.sayName(); // undefined
```

```js
const obj = {
    name: 'licat',
    sayName: function () {
        const arrow = () => {
            // obj.sayName()으로 호출 → this는 obj를 가리킴 (arrow도 this를 obj로 공유)
            console.log(this.name);
        };
        arrow();
    },
};

obj.sayName(); // 'licat'
```

## 1-5. 생성자 함수

-   **새로 생성된 객체** 참조
-   `new` 없이 호출하면 일반 함수처럼 작동하여 전역 객체 참조

```js
function Person(name) {
    this.name = name;
    console.log(this);
}

const p1 = new Person('licat'); // Person { name: 'licat' }
const p2 = Person('mura'); // window.name = 'mura' (브라우저 기준)
```

## 1-6. 이벤트 핸들러

-   이벤트가 발생한 **DOM 요소** 참조

```html
<button id="btn">Click me!</button>

<script>
    const btn = document.getElementById('btn');
    btn.addEventListener('click', function () {
        console.log(this); // <button id="btn">Click me!</button>
    });
</script>
```

> 💡 추가 설명 및 주의 사항
>
> -   화살표 함수에서는 this가 상위 스코프를 따르므로 DOM 요소를 가리키지 않음
>
> ```js
> btn.addEventListener('click', () => {
>     console.log(this); // window
> });
> ```

## 1-7. `call()` & `apply()` & `bind()`

-   `call()` & `apply()`: 함수 실행 시 `this`를 명시적으로 설정
-   `bind()`: 함수 자체의 `this`를 바인딩한 새 함수 반환

```js
function greet() {
    console.log(this.name);
}

const user = { name: 'licat' };

greet.call(user); // 'licat'
greet.apply(user); // 'licat'

const boundGreet = greet.bind(user);
boundGreet(); // 'licat'
```
