# 이미 push한 commit 합치기

## 방법
* git rebase -i 원하는커밋
	* ex) `git rebase -i HEAD~4`
* 합칠 커밋에 squash 표시 후 저장
* 새로운 커밋 메시지를 지정
* `git push origin stage --force`로 push하면 리모트에 적용됨
	* 다른 사람이 pull하지 않은 경우에만 할 것

## 참고
* https://select995.netlify.com/git/commit-merge
* https://json.postype.com/post/209499/