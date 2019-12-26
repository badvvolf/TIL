# Cross origin resource sharing(CORS)

## 개념
* 다른 도메인의 자원을 요청해도 되도록 허용하는 것. HTTP 헤더를 이용하여 권한 설정.
* 브라우저는 특정 도메인의 스크립트로 인해 다른 도메인에 접근하는 것을 막아 XSS를 방어한다.
	* 동일한 출처의 스크립트만 실행되도록 한다. 
	* 하지만 예외적으로 접근을 허용할 도메인을 지정하고 싶을 수도 있다. 이 때 CORS를 이용한다. 허용할 도메인을 CORS를 이용하여 명시한다. 

## 참고
* https://developer.mozilla.org/ko/docs/Web/HTTP/Access_control_CORS
* https://brownbears.tistory.com/336