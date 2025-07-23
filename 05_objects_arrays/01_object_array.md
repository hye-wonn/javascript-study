객체 리터럴, 배열 기초 구조

# 1. 객체 타입

## 1-1. 객체 타입의 특징

-   **값을 변경할 수 있는(참조형)** 데이터

```js
let arr = [1, 2, 3];
arr[0] = 100;

console.log(arr); // [100, 2, 3]
```

# 2. 배열

## 2-1. 배열의 특징

-   데이터를 순서대로 저장하는 **객체**
-   다양한 자료형 포함
-   요소 추가, 제거, 정렬, 검색 등의 작업 가능

### 2-1-1. 배열 생성

-   `[]`를 사용하여 생성
-   `new Array()`를 사용하여 생성 (권장 X)
-   `const`로 선언해도 **요소 변경 가능** (참조 주소값만 고정)

```js
const arr1 = [];
const arr2 = [1, 2, 3];
const arr3 = new Array(4, 5, 6);
const arr4 = new Array(3); // 길이만 지정된 배열

console.log(arr1); // []
console.log(arr2); // [1, 2, 3]
console.log(arr3); // [4, 5, 6]
console.log(arr4); // [ <3 empty items> ]
```

### 2-1-2. 배열 요소 접근

-   **인덱스(0부터 시작)**를 통해 요소에 접근
-   존재하지 않는 인덱스는 `undefined` 반환

```js
const arr = [10, 20, 30];
console.log(arr[0]); // 10
console.log(arr[1]); // 20
console.log(arr[2]); // 30
console.log(arr[3]); // undefined
```

### 2-1-3. 배열의 길이

-   `.length`를 통해 배열의 **길이(요소 개수)** 파악

```js
const arr = [10, 20, 30, 40, 50];
console.log(arr.length); // 5
```

### 2-1-4. 다차원 배열

-   2차원 배열 → 행렬과 동일한 구조 (인덱스 두 번 사용)

```js
const matrix = [
    [1, 2],
    [3, 4],
    [5, 6],
];
console.log(matrix[0][0]); // 1
console.log(matrix[2][1]); // 6

const threeD = [
    [
        [1, 2],
        [3, 4],
    ],
    [
        [5, 6],
        [7, 8],
    ],
];
console.log(threeD[0][1][0]); // 3
console.log(threeD[1][0][1]); // 6
```

## 2-2. 배열의 주요 메서드

### 2-2-1. `push()` & `pop()`

-   `push()`: 배열 끝에 요소 추가
-   `pop()`: 마지막 요소 제거 및 반환

```js
const arr = [1, 2, 3];
arr.push(4);
console.log(arr); // [1, 2, 3, 4]

const last = arr.pop();
console.log(last); // 4
console.log(arr); // [1, 2, 3]
```

### 2-2-2. `shift()` & `unshift()`

-   `shift()`: 첫 번째 요소 제거 및 반환
-   `unshift()`: 배열 앞에 요소 추가

```js
const fruits = ['사과', '바나나', '수박'];
const front = fruits.shift();
console.log(front); // '사과'
console.log(fruits); // ['바나나', '수박']

fruits.unshift('오이', '배');
console.log(fruits); // ['오이', '배', '바나나', '수박']
```

### 2-2-3. `slice(start, end-1)`

-   배열의 일부분을 **새로운 배열**로 반환 (원본 배열 변경 X)

```js
const arr = ['apple', 'banana', 'cherry', 'durian', 'elderberry'];
console.log(arr.slice(1, 4)); // ['banana', 'cherry', 'durian']
console.log(arr.slice(2)); // ['cherry', 'durian', 'elderberry']
console.log(arr.slice()); // 전체 복사
```

### 2-2-4. `sort()`

-   문자열 정렬 → 정상 작동
-   숫자 정렬 → `compareFunction` 사용

```js
// 문자열 정렬
const words = ['banana', 'apple', 'cherry'];
console.log(words.sort()); // ['apple', 'banana', 'cherry']

// 숫자 정렬
const nums = [23, 5, 1000, 42];
console.log(nums.sort()); // [1000, 23, 42, 5] → 의도와 다름

nums.sort((a, b) => a - b);
console.log(nums); // [5, 23, 42, 1000]
```

### 2-2-5. `forEach()`

-   배열의 모든 요소에 대해 함수 실행 (반환값 X)

```js
const fruits = ['참외', '키위', '감귤'];

fruits.forEach((item, index) => {
    console.log(item, index);
});
// 참외 0
// 키위 1
// 감귤 2
```

### 2-2-6. `map()`

-   배열의 각 요소를 **가공하여 새로운 배열로 반환**

```js
const arr = [1, 2, 3];
const newArr = arr.map((item, index) => item * index);
console.log(newArr); // [0, 2, 6]

const data = [
    { name: 'John', age: 28 },
    { name: 'Jane', age: 32 },
];
const ages = data.map((item) => item.age);
console.log(ages); // [28, 32]
```

### 2-2-7. `includes()`

-   특정 값이 **배열에 포함되어 있는지 여부**를 확인 (대소문자 구분)

```js
const arr = ['hello', 'world'
console.log(arr.includes('world')); // true
console.log(arr.includes('JavaScript')); // false
```

### 2-2-8. `join()`

-   배열 요소를 **문자열로 결합** (구분자 지정 가능)

```js
const arr1 = ['hello', 'world'];
console.log(arr1.join('!')); // "hello!world"

const phone = ['010', '1234', '5678'];
console.log(phone.join('-')); // "010-1234-5678"

const binary = [0b100, 0o100, 0x100];
console.log(binary.join(' | ')); // "4 | 64 | 256"
```

### 2-2-9. `find()`

-   조건에 맞는 **첫 번째 요소를 반환** (못 찾으면 `undefined`)

```js
const numbers = [10, 20, 30];
const found = numbers.find((num) => num > 15);
console.log(found); // 20
```

### 2-2-10. `filter()`

-   조건에 맞는 요소들만 **새로운 배열**로 반환

```js
const numbers = [10, 20, 30, 40];
const filtered = numbers.filter((num) => num > 25);
console.log(filtered); // [30, 40]
```

### 2-2-11. `reduce()`

-   배열의 요소를 누적 계산하여 하나의 결과값 반환

```js
array.reduce((누적값, 현재값, 현재인덱스, 원본배열) => {}, 초기값);
```

> 💡 설명
>
> `acc`: 누적 값 (Accumulator)
> `cur`: 현재 처리 중인 요소 (Current Value)
> `index` (선택): 현재 요소의 인덱스
> `array` (선택): reduce를 호출한 배열
> `initialValue`: 누적값의 초기값

```js
const nums = [1, 2, 3, 4];
const total = nums.reduce((acc, cur) => acc + cur, 0);
console.log(total); // 10
```

```js
const arr = ['a', 'b', 'c'];

const result = arr.reduce((acc, cur, idx, array) => {
    console.log('acc:', acc); // 누적값
    console.log('cur:', cur); // 현재값
    console.log('idx:', idx); // 현재 인덱스
    console.log('array:', array); // 원본 배열
    console.log('------------------');

    return acc + `(${idx}:${cur}) `;
}, '');

console.log('최종 결과:', result);

// acc:
// cur: a
// idx: 0
// array: ['a', 'b', 'c']
// ------------------
// acc: (0:a)
// cur: b
// idx: 1
// array: ['a', 'b', 'c']
// ------------------
// acc: (0:a) (1:b)
// cur: c
// idx: 2
// array: ['a', 'b', 'c']
// ------------------
// 최종 결과: (0:a) (1:b) (2:c)
```
