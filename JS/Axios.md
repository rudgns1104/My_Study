# Axios

`2023-07-16`
Axios는 JavaScript에서 사용되는 HTTP 클라이언트 라이브러리이다.

> 브라우저, Node.js를 위한 Promise API를 활용하는 HTTP 비동기 라이브러리
>
> > JavaScript에는 fetch api가 있지만, 프레임워크에서 ajax를 구현할 때는 Axios를 쓴다.

---

<br>

# Axios의 특징

## 간단한 API사용

- Axios는 간결한 API를 제공한다.
- HTTP 요청을 보내기 위해 간단한 메서드를 호출하고, 응답을 Promise 객체로 받아 처리할 수 있다.
  > 이러한 API 디자인은 개발자들이 쉽게 사용하고 익힐 수 있게 도와준다.

## 브라우저 및 Node.js 지원

- Axios는 브라우저와 Node.js 모두에서 동작한다.
- 서버 사이드 렌더링(SSR)을 포함한 다양한 환경에서 사용할 수 있다.

## Promise(ES6) API 사용

- Axios는 Promise 기반 API를 사용한다.
- 비동기 요청을 처리하고, `.them()`및`.catch()`와 같은 Promise 체인을 사용하여 요청의 성공 또는 실패를 처리할 수 있다.
- `async/await`와 함께 사용하여 비동기 코드를 더 읽기 쉽고 유지 보수하기 쉽게 작성할 수 있다.

## 요청 및 응답 인터셉터

- Axios는 요청 및 응답을 인터셉트하여 처리할 수 있는 인터셉터(interceptor)기능을 제공한다.
- 요청 전에 헤더를 수정하거나, 응답 데이터를 가공하거나, 에러를 처리하는 등의 작업을 수행할 수 있다.
  > 글로벌 레벨과 개별 요청 레벨에서 사용할 수 있다.

## 요청 및 응답 데이터 변환

- Axios는 자동으로 요청과 응답 데이터를 변환할 수 있다.
- 예로 JSON 형식으로 데이터를 보낼 수 있고, 응답으로 받은 JSON 데이터를 자동으로 JavaScript 객체로 변환할 수 있다.
  > FormData, Blob, ArrayBuffer 등 다른 유형의 데이터도 처리할 수 있다.

## 오류 처리

- Axios는 HTTP 요청 중 발생하는 오류를 쉽게 처리할 수 있다.
- 네트워크 오류, 요청/응답 상태 코드 오류 등 다양한 오류를 `.catch()` 메서드를 사용하여 오류 처리 로직을 작성할 수 있다.

## 요청 취소

- Axios는 요청 취소 기능을 제공한다.
- 진행 중인 요청을 중단하고 요청이 완료되지 않도록 할 수있다.
  > 요청을 중단해야 하는 경우나 사용자가 요청을 취소하는 경우에 유용하다.

---

<br>

# Axios 사용법

```jsx
axios
  .get("/api/users")
  .then(function (response) {
    // 요청 성공 시 처리할 작업
    console.log(response.data);
  })
  .catch(function (error) {
    // 요청 실패 시 처리할 작업
    console.error(error);
  });
```

코드 설명 :

- `axios.get`은 `/api/users`URL로 GET 요청을 보내고, 응답을 Promise 객체로 반환한다.
- `then` 메서드는 요청이 성공했을 때 호출되고, `catch` 메서드는 요청이 실패했을 때 호출된다.

> 간단하게 사용한 예시

```jsx
import axios from "axios";
import React, { useEffect, useState } from "react";

const Index = () => {
const [posts, setPosts] = useState([]);

useEffect(() => {
   axios({
     method: "GET",
     url: "https://jsonplaceholder.typicode.com/photos",
   }).then((Response) => setPosts(Response.data));
```

> 더 축약한 버전

```jsx
axios
  .get("https://jsonplaceholder.typicode.com/photos")
  .then((Response) => setPosts(Response.data));
```
