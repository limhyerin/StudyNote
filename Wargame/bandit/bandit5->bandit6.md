# 🌳bandit5 -> bandit6🌳
> The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties: <br/>

- human-readable 
- 1033 bytes in size 
- not executable

다음 레벨의 비밀번호는 inhere 디렉토리 아래 파일 어딘가에 존재하는데 다음과 같은 속성을 가지고 있다 <br />
그래서 사람만이 읽을 수 있으며 1033bytes의 사이즈이며 실행시킬 수 없는 파일을 찾아보면 된다.

<br/>

**hint commands**
>ls , cd , cat , file , du , find


- file : 파일 종류(type) 확인 <br/>
- du(disk usage) : 파일, 디렉토리 용량 확인 <br/>
- find : 파일 검색 <br/>

|명령어|뜻|
|------|---|
|-name|해당 이름의 파일을 찾음. 해당 이름에는 정규 표현식을 활용할 수 있음|
|-type|지정된 파일 타입에 해당하는 파일 검색|
|-user|해당 유저에게 속한 파일 검색|
|-empty|빈 디렉토리 혹은 크기가 0인 파일 검색|
|-delete|검색된 파일 혹은 디렉토리 삭제|
|-exec|검색된 파일에 대해 지정된 명령 실행|
|-path|지정된 문자열 패턴에 해당하는 경로에서 검색|
|-print|검색 결과를 출력. 검색 항목은 newline으로 구분. (기본 값)|
|-print0|검색 결과를 출력. 검색 항목은 null로 구분|
|-size|파일 크기를 사용하여 파일 검색|
|-mindepth|검색을 시작할 하위 디렉토리 최소 깊이 지정|
|-maxdepth|검색할 하위 디렉토리의 최대 깊이 지정|
|-atime|n일 이내에 액세스된 파일을 찾음|
|-ctime|n일 이내에 만들어진 파일을 찾음|
|-mtime|n일 이내에 수정된 파일을 찾음|
|-cnewer file|해당 파일보다 최근에 수정된 파일을 찾음|

[출처]https://coding-factory.tistory.com/804

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

### 04 file 명령어 사용 : 1033 byte 파일 찾기
❗ 1033 byte 사이즈인 파일을 찾기 위해 file -size 1033을 해주었더니 아무것도 뜨지 않는다. <br/>
```ssh
bandit5@bandit:~/inhere$ find -size 1033
```

찾아보니 size를 찾을때 파일 크기 단위를 붙여주어야했다
- b : 블록단위
- c : byte
- k : kbyte
- w : 2byte 워드

byte는 뒤에 c를 붙여주어야하기 때문에 붙여서 검색해주면 조건에 해당하는 파일의 위치가 나온다.
```ssh
bandit5@bandit:~/inhere$ find -size 1033c
./maybehere07/.file2
```

해당 위치의 파일 내용을 확인해주면 password를 얻을 수 있다.
```ssh
bandit5@bandit:~/inhere$ cat ./maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG
```
