# Best-fit Mappings
* 문자 X가 완전히 다른 문자 Y로 변환되는 경우 
	* 프레임워크 API가 입력받은 값을 다른 인코딩으로 변환하는 경우 (디폴트로)
	* UTF-16과 같은 멀티바이트 인코딩을 US-ASCII와 같은 싱글바이트 인코딩으로 변환하는 경우
	* 문자 X가 변환하려는 인코딩에 없는 경우. 소프트웨어는 가장 맞는(best-fit) 문자를 찾으려 한다. 
	* 윈도우 환경에서 잘 일어난다고 함

## 예시
* `U+FF1C FULLWIDTH LESS-THAN SIGN` 를 `U+003C LESS-THAN SIGN` 또는 `ASCII 0x3C` 로 변환
	* FULLWIDTH 는 문자의 폭이 더 넓은 형태를 의미한다. 모두 `<` 문자를 의미하지만 완전히 다른 바이너리가 된다. 
	* 입력시 U+FF1C -> 백엔드 API에서 windows-1252 로 인코딩 변환 : FF1C 가 3C가 됨 -> 원래 필터링하던 3C가 필터링을 우회하는 결과


## 참고
* http://websec.github.io/unicode-security-guide/