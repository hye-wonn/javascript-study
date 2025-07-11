# 1. 웹 브라우저 구성 요소

-   HTML: 웹 페이지의 구조와 내용 (e.g. 제목, 문단, 목록, etc.)
-   CSS: 웹 페이지의 디자인 (e.g. 색상, 글꼴, 배치, etc.)
-   JavaScript: 웹 페이지 동작 정의 (e.g. 클릭 시 반응, 값 계산, 서버와 통신, etc.)

# 2. JavaScript 사용 방법

## 2-1. HTML 내 직접 삽입

### 2-1-1. 인라인 방식 (태그 속성에 삽입)

```html
<button onclick="window.alert('Hello');">인사하기</button>
```

### 2-1-2. 내부 `<script>` 태그에 작성

```html
<!DOCTYPE html>
<html lang="ko">
    <head> </head>
    <body>
        <script>
            window.alert('hello world!');
        </script>
    </body>
</html>
```

## 2-2. 외부 스크립트 파일 연결

### 2-2-1. 연결 방식

1. `.js` 파일 별도 생성 (e.g. `main.js`)
2. HTML 파일에서 `<script src="파일 이름"></script>`로 불러오기

```html
<!DOCTYPE html>
<html lang="ko">
    <head> </head>
    <body>
        <script src="test.js"></script>
    </body>
</html>
```

### 2-2-2. 장점

-   코드 재사용성 증가
-   유지보수 편리
-   HTML과 JS 코드 분리로 가독성 향상

## 2-3. 콘솔 (Ctrl + Shift + i)

-   코드의 동작 확인 및 디버깅을 돕는 브라우저 도구
-   간단한 코드 테스트, 디버깅에 유용

> 💡 `about:blank` 페이지에서 JavaScript 연습 가능
