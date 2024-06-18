# 🌳bandit3 -> bandit4🌳
>The password for the next level is stored in a hidden file in the inhere directory.<br/>

다음 레벨의 비밀번호는 inhere 디렉토리 안의 숨겨진 파일(hidden file) 안에 있다.

<br/>

## ☀️해결☀️
### 01 ls -l 명령어 사용 : 파일 확인
👉 홈 디렉토리에서 ls -l 명령어를 통해 현재 위에 있는 파일을 확인한다. <br/>
```ssh
bandit3@bandit:~$ ls -l
total 4
drwxr-xr-x 2 root root 4096 Jun 16 02:48 inhere
```

<br/>

### 02 cd 명령어 : 위치 이동
👉 cd 명령어를 통해 inhere 디렉토리 내부로 이동한다. <br/>
```ssh
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$
```

<br/>

### 03 ls -al : 숨겨진 파일 확
👉 홈 디렉토리에서 ls -al 명령어를 통해 현재 위에 있는 숨겨진 파일도 다 같이 확인한다. <br/>
```ssh
bandit3@bandit:~/inhere$ ls -al
total 12
drwxr-xr-x 2 root    root    4096 Jun 16 02:48 .
drwxr-xr-x 3 root    root    4096 Jun 16 02:48 ..
-rw-r----- 1 bandit4 bandit3   33 Jun 16 02:48 ...Hiding-From-You
```

<br/>

### 04 cat 명령어 사용 : 파일 내용 확인
💡 숨겨진 파일의 내용을 확인하면 비밀번호를 얻을 수 있다<br/>
```ssh
bandit3@bandit:~/inhere$ cat ...Hiding-From-You
2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ
```
