# Headless 커밋 포함하기
* 가끔 submodule을 이용하다보면 push를 해도 Everything up-to-date 라며 되지 않는다. 이 때는 새로운 커밋이 Headless 커밋일 수 있다. 
* checkout을 하면 Headless 커밋이 있을 때 이를 경고하기도 한다. 

```bash
git checkout master
git merge HEAD@{1}
git push origin master
```

##  참고
* https://stackoverflow.com/questions/4445738/unable-to-push-commits-from-a-git-submodule