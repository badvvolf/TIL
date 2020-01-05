# Domain fronting

## 개념
* HTTPS 연결의 도메인 정보를 난독화(또는 다른 도메인에 접속하는 척 가장)하여 인터넷 검열을 우회
* CDN을 사용하는 도메인만 가능
* 처음 SNI 필드는 다른 도메인(동일한 CDN을 이용하는)을 넣어 차단되지 않도록 함. HTTPS로 실제 통신을 시작하면 Host로 원하는 도메인 설정


## 참고
* https://ko.wikipedia.org/wiki/%EB%8F%84%EB%A9%94%EC%9D%B8_%ED%94%84%EB%A1%A0%ED%8C%85
* http://blog.daum.net/nordvpn.kr/32
* https://blog.naver.com/aepkoreanet/221468896445