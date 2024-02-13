# 🛠️ 발생한 문제 🛠️
React 프로젝트 Git clone 해왔는데 npm start가 안되는 문제가 발생

<br/>

# 🔔 해결 🔔
npm install을 통해 다시 패키지를 설치해주어야 한다. <br/>
```
git clone https://github.com/{username}/{repo-name}.git
cd {repo-name} // 로컬 프로젝트 폴더로 들어감 
npm install
npm start
```
명령어 치고 push 할 것
```
git remote set-url origin "재설정할 깃헙주소"
```
