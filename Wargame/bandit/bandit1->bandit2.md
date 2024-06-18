# 🌳bandit1 -> bandit2🌳
>The password for the next level is stored in a file called - located in the home directory <br/>

다음 레벨의 비밀번호는 홈 디렉토리(home directory)안의 -라는 폴더 안에 있다.

<br/>

## ☀️해결☀️
### 01 ls -l 명령어 사용 : 파일 확인
👉 홈 디렉토리에서 ls -l 명령어를 통해 현재 홈 디렉토리 안에 있는 파일을 확인한다. <br/>
```ssh
bandit1@bandit:~$ ls -l
total 4
-rw-r----- 1 bandit2 bandit1 33 Jun 16 02:47 -
```

<br/>

### 02 cat 명령어 사용 : 파일 내용 확인
❗ cat 명령어를 통해 해당 파일의 내용물을 확인해주면 되는데 바로 -를 쓰면 파일명으로 인식하지 못한다. 그래서 해당 파일 안에 저장되어 있는 비밀번호 정보를 불러올 수가 없다. <br/>
```ssh
bandit1@bandit:~$ cat -


^C
```

<br/>

💡 그래서 현재 위치 밑에 있는 - 폴더를 찾기 위해 cat ./-로 해주면 비밀번호를 찾을 수 있다. <br/>
```ssh
bandit1@bandit:~$ cat ./-
263JGJPfgU6LtdEvgfWU1XP5yac29mFx
```
