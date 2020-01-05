# CDN과 DNS

## 개념
* DNS 쿼리를 하면 실제 서버 IP가 아닌 이상한 IP가 온다. CNAME도 마찬가지. 이는 CDN 서버로 즉 캐시서버이다. 
* 캐시 서버 DNS는 DNS 쿼리를 한 위치와 가까운 캐시 서버를 준다. 구글 네임서버를 이용하여 DNS 쿼리를 할 경우 구글 DNS 서버 위치와 가까운 캐시 서버를 준다. 그래서 보통 미국쪽 서버가 온다. 
* 캐시가 아닌 실제 IP를 받으려면 CDN 서버를 우회해야 한다. [참고](https://topic.alibabacloud.com/a/11-ways-to-bypass-cdn-to-find-real-ip_8_8_31062138.html)

## 참고
* https://www.netmanias.com/ko/post/blog/5359/akamai-cdn-dns-google-network-protocol/answer-google-dns-akamai-cdn
* https://topic.alibabacloud.com/a/11-ways-to-bypass-cdn-to-find-real-ip_8_8_31062138.html