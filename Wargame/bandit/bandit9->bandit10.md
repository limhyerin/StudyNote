# 🌳bandit9 -> bandit10🌳
> The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters. <br/>

다음 레벨의 비밀번호는 여러 개의 '=' 문자 앞에 사람이 읽을 수 있는 소수의 문자열 중 하나로 data.txt 파일에 저장된다 <br />

<br/>

**hint commands**
>grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

- grep : 파일 내 특정 문자열 검색
- uniq : 중복된 내용 제거
- strings : 문자열만 추출하여 출력
- tr : 지정한 문자를 변환하거나 삭제
- tar : 여러 개의 파일을 하나의 파일로 묶거나 풀때 사용
- gzip : 압축

<br />

## ☀️해결☀️
### 01 ls -l 명령어 사용 : 파일 확인
👉 ls -l 명령어를 통해 현재 위치에 있는 data.txt 파일을 확인한다.<br/>
```ssh
bandit9@bandit:~$ ls -l
total 20
-rw-r----- 1 bandit10 bandit9 19379 Jun 16 02:47 data.txt
```

<br/>

문풀중~~
