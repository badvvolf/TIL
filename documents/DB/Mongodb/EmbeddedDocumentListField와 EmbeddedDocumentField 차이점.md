# EmbeddedDocumentListField와 EmbeddedDocumentField 차이점

* ListField(EmbeddedDocumentField)가 아니라 EmbeddedDocumentListField를 사용하면 유용한 메소드를 더 이용할 수 있다. 
* count(), filter(), delete(), create() 와 같은 메소드 이용 가능
* 오브젝트로 접근하기도 편리하다. 

## 참고

* https://stackoverflow.com/questions/50133620/mongoengine-difference-between-embeddeddocumentlistfield-and-listfieldembedd