(220512)

# Uncaught TypeError: undefined in removeCookie

<나혼자탄다 프로젝트:로그인기능 구현 중.. >

### 서사

서버에서 클라이언트로 JWT Token을 보낸 후 클라이언트는 JWT Token을 Cookie에 저장한다. 저장했다면 브라우저 검사-> 애플리케이션->쿠키 에서 저장된 이름, 값을 볼 수 있는데 저런 메세지만 떴다.

### 해결방법

- 상단에 명시해준다.

```js
<script src="https://cdnjs.cloudflare.com/ajax/libs/jquery-cookie/1.4.1/jquery.cookie.js">
```

# html 중 onclick이벤트 발생 시 button구동이 되지 않을때

- type이 들어가있는지 확인
  `<button type="button">`

#
