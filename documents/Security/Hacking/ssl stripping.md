# SSL stripping

## 개념
* SSL Downgrade Attack 이라고도 함
* 로그인 등 중요 데이터를 전송할 때, 서버가 HTTPS로 변환하기를 유도한다. 이를 MITM으로 HTTP URL로 변경한다. 사용자는 HTTP로 로그인 정보를 전송하게 된다. 
* [HSTS](/documents/Network/HTTP)로 방어할 수 있음

## 참고
* http://blog.skinfosec.com/220601267742
* https://security.stackexchange.com/questions/41988/how-does-sslstrip-work