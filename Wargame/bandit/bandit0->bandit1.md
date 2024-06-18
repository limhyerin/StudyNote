# 🌳bandit0 -> bandit1🌳
>The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game. <br/>

다음 레벨의 비밀번호는 readme 라는 파일 안에 저장되어 있는데 그것은 홈 디렉토리(home directory)에 있다. 

<br/>

## ☀️해결☀️
### 01 ls -l 명령어 사용 : 파일 확인
👉 홈 디렉토리에서 ls -l 명령어를 통해 현재 홈 디렉토리 안에 있는 파일을 확인한다. <br/>
```ssh
bandit0@bandit:~$ ls -l
total 4
-rw-r----- 1 bandit1 bandit0 437 Jun 16 02:47 readme
```

<br/>

### 02 cat 명령어 사용 : 파일 내용 확인
👉 cat 명령어를 통해 해당 파일의 내용물을 확인해주면 끝 <br/>
```ssh
bandit0@bandit:~$ cat readme
Congratulations on your first steps into the bandit game!!
Please make sure you have read the rules at https://overthewire.org/rules/
If you are following a course, workshop, walthrough or other educational activity,
please inform the instructor about the rules as well and encourage them to
contribute to the OverTheWire community so we can keep these games free!

The password you are looking for is: ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If
```
