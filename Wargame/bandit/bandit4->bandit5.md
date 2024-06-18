# 🌳bandit4 -> bandit5🌳
>The password for the next level is stored in the only human-readable file in the inhere directory.
>Tip: if your terminal is messed up, try the “reset” command. <br/>

다음 레벨의 비밀번호는 inhere 디렉토리 안의 사람만 읽을 수 잇는 파일이 있는데 그 안에 저장되어있다. <br />
팁 : 터미널이 엉망되면 리셋하라.

<br/>

## ☀️해결☀️
### 01 ls -l 명령어 사용 : 파일 확인
👉 홈 디렉토리에서 ls -l 명령어를 통해 현재 위에 있는 파일을 확인한다. <br/>
```ssh
bandit4@bandit:~$ ls -l
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

### 03 ls -l : 파일 목록 확인
👉 홈 디렉토리에서 ls -l 명령어를 통해 현재 위에 있는 파일 목록을 확인한다. 모두 현재 읽을 수 있는 파일이다.<br/>
```ssh
bandit4@bandit:~/inhere$ ls -l
total 40
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file00
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file01
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file02
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file03
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file04
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file05
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file06
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file07
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file08
-rw-r----- 1 bandit5 bandit4 33 Jun 16 02:48 -file09
```

<br/>

### 04 cat 명령어 사용 : 파일 내용 확인
💡 사람이 읽을 수 있는 파일에 password가 있다고 했기 때문에 각각의 파일을 하나하나 확인해주어야한다. <br/>
```ssh
bandit4@bandit:~/inhere$ cat ./-file00
ˊu▒_▒}▒▒R▒▒▒O▒CxQ▒r▒▒j▒▒C3!▒bandit4@bandit:~/inhere$
```
```ssh
bandit4@bandit:~/inhere$ cat ./-file01
Jx▒o▒▒-|▒▒▒eYq▒▒▒SP kC▒L▒▒▒▒bandit4@bandit:~/inhere$
```
```ssh
bandit4@bandit:~/inhere$ cat ./-file02
▒Њya▒<NO#▒H▒▒▒▒▒▒]▒6▒▒$▒▒bandit4@bandit:~/inhere$
```
```ssh
bandit4@bandit:~/inhere$ cat ./-file03
;L▒▒▒▒7▒η▒!S▒▒�.▒)▒▒4%▒w2▒bandit4@bandit:~/inhere$
```
```ssh
bandit4@bandit:~/inhere$ cat ./-file04
▒(▒F▒obandit4@bandit:~/inhere$
```
```ssh
bandit4@bandit:~/inhere$ cat ./-file05
ҵ▒▒W▒▒ӗ;▒T▒▒P
Cў▒i ƾ▒>x▒bandit4@bandit:~/inhere$
```
```ssh
bandit4@bandit:~/inhere$ cat ./-file06
▒▒37x?▒=▒h▒▒*peN&▒▒I"▒{▒bandit4@bandit:~/inhere$
```
```ssh
bandit4@bandit:~/inhere$ cat ./-file07
4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw
bandit4@bandit:~/inhere$
```
