# 🌳bandit1 -> bandit2🌳
The password for the next level is stored in a file called - located in the home directory

<br/>

다음 레벨의 비밀번호는 홈 디렉토리(home directory)안의 -라는 폴더 안에 있다.

<br/>

## ☀️해결☀️
홈 디렉토리에서 ls -l 명령어를 통해 현재 홈 디렉토리 안에 있는 파일을 확인한다. <br/>
![image](https://github.com/limhyerin/StudyNote/assets/70150896/c02e7bf3-cd64-4e61-bf22-0ba8f1080261)

<br/>

cat 명령어를 통해 해당 파일의 내용물을 확인해주면 되는데 바로 -를 쓰면 파일명으로 인식하지 못한다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/faa7b252-cffc-434b-8002-497229c05fcf)

<br/>

그래서 현재 위치 밑에 있는 - 폴더를 찾기 위해 cat ./-로 해주면 비밀번호를 찾을 수 있다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/36ab518d-f0da-4408-9fdc-8c7b28b0556f)
