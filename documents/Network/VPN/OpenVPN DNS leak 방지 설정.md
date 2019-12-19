# OpenVPN DNS leak 방지 설정

## .ovpn
### Windows
* `block-outside-dns` 를 추가한다. 
	* WFP(Windows Filtering Platform)로 인해 VPN 외의 DNS에 접근하는 것을 막기 위한 옵션이다. 
	* **리눅스 기반인 공유기에 VPN을 붙일 때 이 설정을 추가하면 에러가 난다.**

## 참고
* https://www.dnsleaktest.com/