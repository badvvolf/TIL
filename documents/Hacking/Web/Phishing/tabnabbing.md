# Tabnabbing
## 개념
* HTML 문서에서 링크 클릭 시 새롭게 열린 탭에서 기존 문서의 location을 피싱 사이트로 변경한다. 
	* 앵커 태그의 target이 \_blank인 것만 가능. target \_blank는 새 창이나 새 탭에서 열리는 속성이다.
	* 링크를 클릭하여 연 페이지에서 자바스크립트를 이용해 opener의 location을 피싱 사이트로변경
	* 새로 연 탭에서 다시 기존 탭으로 이동하면 기존 탭이 피싱 사이트에 접속해 있다. 



링크 게시 사이트

```HTML
<a target=_blank href=http://example.com/watch_this>hello</a>
```

watch_this 내용
```HTML
<script>
window.opener.location = "http://evil.com"
</script>
```

evil.com 내용
```HTML
피싱 사이트 내용
```


## 방어
* 앵커 태그에 rel="noopener noreferrer" 속성 추가
	* noopener : 링크를 오픈한 window.opener 값을 설정하지 않음
	* noreferrer : referer 정보를 보내지 않음


## 참고
* https://blog.coderifleman.com/2017/05/30/tabnabbing_attack_and_noopener/
* https://www.owasp.org/index.php/Reverse_Tabnabbing
