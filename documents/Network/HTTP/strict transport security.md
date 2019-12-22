# Strict transport security

## 개념
* HTTP Strict Transport Security 헤더는 웹사이트가 브라우저에게 절대로 HTTP 로 사이트를 연결하면 안되고 HTTP 로 연결하려는 모든 시도는 자동으로 HTTPS로 변경해야 된다고 알린다
	* 300번대로 응답코드로 리다이렉트하게 함
* HTTP로 이 헤더를 전송하는 경우에는 무시해야 함
	* 조작되어 끼워넣어진 헤더일수도 있기 때문
## 참고
* https://developer.mozilla.org/ko/docs/Web/HTTP/Headers/Strict-Transport-Security