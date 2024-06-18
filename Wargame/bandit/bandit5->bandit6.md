# 🌳bandit5 -> bandit6🌳
> The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties: <br/>

>human-readable <br/>
1033 bytes in size <br/>
not executable <br/>

다음 레벨의 비밀번호는 inhere 디렉토리 아래 파일 어딘가에 존재하는데 다음과 같은 속성을 가지고 있다 <br />
그래서 사람만이 읽을 수 있으며 1033bytes의 사이즈이며 실행시킬 수 없는 파일을 찾아보면 된다.

<br/>

**hint commands**
>ls , cd , cat , file , du , find

<br />

## ☀️해결☀️
### 01 ls -l 명령어 사용 : 파일 확인
👉 홈 디렉토리에서 ls -l 명령어를 통해 현재 위에 있는 파일을 확인한다. <br/>
```ssh
bandit5@bandit:~$ ls -l
total 4
drwxr-x--- 22 root bandit5 4096 Jun 16 02:48 inhere
```

<br/>

### 02 cd 명령어 : 위치 이동
👉 cd 명령어를 통해 inhere 디렉토리 내부로 이동한다. <br/>
```ssh
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$
```

<br/>

### 03 ls -l : 파일 목록 확인
👉 홈 디렉토리에서 ls -l 명령어를 통해 현재 위치에 있는 파일/디렉토리의 목록을 확인한다. <br/>
```ssh
bandit5@bandit:~/inhere$ ls -l
total 80
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere00
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere01
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere02
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere03
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere04
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere05
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere06
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere07
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere08
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere09
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere10
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere11
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere12
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere13
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere14
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere15
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere16
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere17
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere18
drwxr-x--- 2 root bandit5 4096 Jun 16 02:48 maybehere19
```

<br/>

### 04 cat 명령어 사용 : 파일 내용 확인
💡 해당 파일들이 모두 디렉토리여서 일일히 다 찾아볼 수도 있지만 명령어를 사용해서 해당 조건에 맞는 파일을 찾아 줄 수 있다. <br/>
```ssh
bandit4@bandit:~/inhere$ cat ./-file00
ˊu▒_▒}▒▒R▒▒▒O▒CxQ▒r▒▒j▒▒C3!▒bandit4@bandit:~/inhere$
```
