# 하나의 리눅스에서 OpenVPN Client 여러 개 돌리기

## 리눅스 네임스페이스 이용
리눅스 네트워크 네임스페이스를 정의하고, 그 네임스페이스에서 OpenVPN을 붙인다. 그리고 해당 네임스페이스를 이용하는 셸을 새로 만들어 작업한다. 그 셸은 그 VPN을 사용한다. 

## 참고 
https://github.com/slingamn/namespaced-openvpn/blob/master/namespaced-openvpn