# Embedded 오브젝트 업데이트 하기

* Embedded 오브젝트의 경우 add_to_set 과 같은 옵션이 update에서 먹히지 않을 수 있다. 사용이 불가하다면 공식 문서에서 언급하므로 공식 문서를 자세히 읽어보자. 

Nested Embedded 오브젝트 업데이트 하기 예시
```python
obj = SomeModel.objects(name=name)
임베디드obj = obj.임베디드이름1.get(조건=조건).임베디드이름2.get(조건=조건)
임베디드obj.리스트변수.extend(source)
```
이러면 자동으로 DB에 저장된다. 

## 참고
* http://docs.mongoengine.org/apireference.html#mongoengine.base.datastructures.EmbeddedDocumentList.update