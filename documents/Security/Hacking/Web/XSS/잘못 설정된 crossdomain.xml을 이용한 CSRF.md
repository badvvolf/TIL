# 잘못 설정된 crossdomain.xml을 이용한 CSRF

## 개념
* Victim이 관대한 크로스 도메인 규정을 이용하는 경우 공격자가 방어를 우회하여 CSRF 할 수 있다. 
* 클라이언트가 공격자의 페이지에 접속하여 악성 플래시 등을 통해 Victim에 요청 -> 크로스도메인 규칙이 관대하여 공격자 도메인으로부터 발생한 요청에 응답함 -> 이를 클라이언트가 다시 공격자에게 전송하도록 하면 정보 유출

## 참고
* https://resources.infosecinstitute.com/bypassing-csrf-protections-fun-profit/
* http://gursevkalra.blogspot.com/2013/08/bypassing-same-origin-policy-with-flash.html
* https://resources.infosecinstitute.com/bypassing-csrf-protections-fun-profit/