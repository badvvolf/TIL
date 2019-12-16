# OAuth

 SNS/특정 사이트 계정으로 로그인하기와 같은 기능에 이용한다. 
 Third party 어플리케이션의 API 등을 호출하는 권한을 얻기 위해 사용한다.

## 용어
`Protected resource`: 권한을 받은 후 사용하고 싶은 자원.
`Client`: 권한을 받아 자원을 사용하고 싶은 어플리케이션. `Consumer` 라고도 함
`User`: 클라이언트를 사용하는 유저
`Resource owner`: 자원 소유자. `Service provider`라고도 함.
`Resource server`: 자원 서버. 검증된 클라이언트에게 자원을 제공해주는 서버.
`Authorization server`: 권한 서버. 

내 홈페이지에 `페이스북 계정으로 로그인하기` 기능을 넣은 상황을 예로 든다면, `Resource owner`는 페이스북, `Client`는 내 홈페이지, `User`는 로그인하고 싶은 접속자이다. 


## 과정

### 토큰 발급

 OAuth를 이용하기 위해서는 먼저 Client측에서 Resource Owner에 OAuth를 사용하겠다고 요청하고, Access Token을 발급받아야 한다. 

```
     +--------+                               +---------------+
     |        |--(A)- Authorization Request ->|   Resource    |
     |        |                               |     Owner     |
     |        |<-(B)-- Authorization Grant ---|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(C)-- Authorization Grant -->| Authorization |
     | Client |                               |     Server    |
     |        |<-(D)----- Access Token -------|               |
     |        |                               +---------------+
     |        |
     |        |                               +---------------+
     |        |--(E)----- Access Token ------>|    Resource   |
     |        |                               |     Server    |
     |        |<-(F)--- Protected Resource ---|               |
     +--------+                               +---------------+

```


Access 토큰에는 사용 기한이 있다. 기한이 지나면 새로운 토큰을 발급해야 한다. 이를 위해 Refresh 토큰을 이용한다. Refresh 토큰을 제출하면 새로운 Access 토큰을 발급받을 수 있다. 

```
  +--------+                                           +---------------+
  |        |--(A)------- Authorization Grant --------->|               |
  |        |                                           |               |
  |        |<-(B)----------- Access Token -------------|               |
  |        |               & Refresh Token             |               |
  |        |                                           |               |
  |        |                            +----------+   |               |
  |        |--(C)---- Access Token ---->|          |   |               |
  |        |                            |          |   |               |
  |        |<-(D)- Protected Resource --| Resource |   | Authorization |
  | Client |                            |  Server  |   |     Server    |
  |        |--(E)---- Access Token ---->|          |   |               |
  |        |                            |          |   |               |
  |        |<-(F)- Invalid Token Error -|          |   |               |
  |        |                            +----------+   |               |
  |        |                                           |               |
  |        |--(G)----------- Refresh Token ----------->|               |
  |        |                                           |               |
  |        |<-(H)----------- Access Token -------------|               |
  +--------+           & Optional Refresh Token        +---------------+
```


### 사용자 인증
https://showerbugs.github.io/2017-11-16/OAuth-%EB%9E%80-%EB%AC%B4%EC%97%87%EC%9D%BC%EA%B9%8C