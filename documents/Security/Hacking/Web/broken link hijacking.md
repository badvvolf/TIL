# Broken Link Hijacking

## 개념
* 만료된 링크, 끊긴 링크를 하이재킹
* 도메인이 만료되었지만 이 도메인으로 향하는 링크는 삭제하지 않았을 경우, 이 도메인을 구매하여 내 페이지로 연결할 수 있다. 

## 공격
### Stored Broken Link Hijacking
#### Stored XSS (External JS File Hijacking)
```HTML 
<body>
	<script src="//example.com/script.js"></script>
</body>
```
example.com 도메인을 사서 /script.js 파일을 두면 Stored XSS가 가능하다. 

#### Information Leakage
* 하이재킹 가능한 링크 중 `rel="noopener noreferrer"` 속성이 없는 경우 정보를 유출할 수 있다. [Tabnabbing](./Phishing/tabnabbing.md)
* 도메인을 구매한 뒤 링크에 해당하는 파일을 생성하지 않으면 여전히 404가 뜨지만, 도메인 관리자로서 트래픽 분석을 할 수도 있음. 정보 유출.

#### Content Hijacking
* 이미지나 비디오와 같은 컨텐츠를 바꿀 수 있음

### Reflected Broken Link Hijacking
* 입력값을 이용하여 URL을 작성하는 경우 가능하다. 
 다음은 입력값으로 version을 받고, 이 버전으로 cdn.example/1.0.0/script.js URL을 완성하여 특정 버전의 자바스크립트를 요청하는 예이다. 
```HTML
<!-- http://example.edu/?version=1.0.0 -->
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>Broken Link Hijacking</title>
</head>
<body>
  <script src="//cdn.example/1.0.0/script.js"></script>
</body>
</html>
```
 입력값을 link=maliciouspath 와 같이 변경하면 URL 위치를 조작하여 링크를 깨트릴 수 있다. (version과 마찬가지로 반사되는 듯) 
 CDN에 파일을 업로드할 수 있다면 링크를 깨트려 다른 파일을 가져가게 할 수도 있다..

```HTML
<!-- http://example.edu/?link=maliciouspath -->
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width">
  <title>Broken Link Hijacking</title>
</head>
<body>
  <script src="//cdn.example/maliciouspath/script.js"></script>
</body>
</html>

```

## 참고
* https://edoverflow.com/2017/broken-link-hijacking/
* http://ghostlulz.com/broken-link-hijacking/
* https://hackernoon.com/how-i-hijacked-top-celebrities-tweets-including-katy-perry-shakira-fca3a0e751c6
* https://github.com/misterch0c/twitterBFTD
* https://github.com/cure53/HTTPLeaks