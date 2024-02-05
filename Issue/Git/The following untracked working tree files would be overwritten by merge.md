## 🛠️발생한 이슈🛠️
```
error: The following untracked working tree files would be overwritten by merge:
        Readme.md
Please move or remove them before you merge.
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/c50a88ff-a735-414a-849e-a8f824e03da8)

## 🤖해결 방법🤖
```bash
git stash --all
```
```bash
git pull origin main
```
```bash
git add .
```
```bash
git commit -m "커밋 메시지"
```
```bash
git push origin main
```
