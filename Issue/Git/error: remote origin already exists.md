# 🚨ERROR CODE🚨
git clone을 해와서 코드를 수정하고 올리려고 할때 문제 발생. 그래서 기존의 branch가 존재하는 것
>error: remote origin already exists.

# 🪄해결🪄
해당 branch를 삭제해주고 다시 remote 해주면 해결 완료
```
git remote remove origin
```
