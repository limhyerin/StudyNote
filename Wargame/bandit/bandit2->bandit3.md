# 🌳bandit2 -> bandit3🌳
>The password for the next level is stored in a file called spaces in this filename located in the home directory <br/>

다음 레벨의 비밀번호는 홈 디렉토리(home directory)안의 space가 들어간 파일 안에 있다.

<br/>

## ☀️해결☀️
### 01 ls -l 명령어 사용 : 파일 확인
👉 홈 디렉토리에서 ls -l 명령어를 통해 현재 홈 디렉토리 안에 있는 파일을 확인한다. <br/>
```ssh
bandit2@bandit:~$ ls -l
total 4
-rw-r----- 1 bandit3 bandit2 33 Jun 16 02:47 spaces in this filename
```

<br/>

### 02 cat 명령어 사용 : 파일 내용 확인
❗ space in this filename이라는 파일이 있는데 해당 파일을 cat 명령어와 함께 그대로 입력하게 되면 공백을 기준으로 각각 다른 파일 확은 디렉토리로 인식해서 오류가 발생하는 것을 볼 수 있다. <br/>
```ssh
bandit2@bandit:~$ cat spaces in this filename
cat: spaces: No such file or directory
cat: in: No such file or directory
cat: this: No such file or directory
cat: filename: No such file or directory
```

<br/>

💡 공백이 들어간 파일을 하나의 파일 혹은 디렉토리로 인식하도록 하기 위해서는 **큰따옴표(")** 혹은 **작은따옴표(')** 를 사용하여 묶어주면 된다 <br/>
```ssh
bandit2@bandit:~$ cat 'spaces in this filename'
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```
```ssh
bandit2@bandit:~$ cat "spaces in this filename"
MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx
```
