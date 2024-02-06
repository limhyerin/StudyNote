# 🚨error code🚨
Git pull시 오류, 아마도 깃허브에 README.MD 파일을 직접 수정해서 적용했는데 그걸 vscode에서 pull을 해오지 않고 커밋한 후 push를 하려고 하다가 문제가 발생해서 이것저것 만져보다보니 문제가 발생한 것 같다.
```
error: The following untracked working tree files would be overwritten by merge:
        Readme.md
Please move or remove them before you merge.
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/c50a88ff-a735-414a-849e-a8f824e03da8)

<br/>

## 1. untracked까지 stash 해주는 옵션
- git stash : 아직 마무리하지 않은 작업을 스택에 잠시 저장할 수 있도록 하는 명령어. 이를 통해 아직 완료하지 않은 일을 commit 하지 않고 나중에 다시 꺼내와 마무리할 수 있음
- 워킹 디렉토리에서 수정한 파일들만 저장
```bash
git stash --all
```

<br/>

## 2. git pull
```bash
git pull origin main
```

<br/>

## 3. git add
```bash
git add .
```

<br/>

## 4. git commit
```bash
git commit -m "커밋 메시지"
```

<br/>

## 5. git push
```bash
git push origin main
```
