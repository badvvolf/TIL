# key가 있는지 판단하기

* json key가 있는지 판단하려면 $exists 선택자를 이용한다. 
`db.inventory.find( { qty: { $exists: true})` 형식으로 이용

## 참고
* https://docs.mongodb.com/manual/reference/operator/query/exists/