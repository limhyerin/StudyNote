# 🌳bandit11 -> bandit12🌳
> The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions <br/>

다음 레벨의 비밀번호는 data.txt 파일에 저장되며, 여기서 모든 소문자(a-z) 및 대문자(A-Z)는 13자리씩 회전되었습니다. <br />

<br/>

**hint commands**
>grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

- grep : 파일 내 특정 문자열 검색
- uniq : 중복된 내용 제거
- strings : 문자열만 추출하여 출력
- tr : 지정한 문자를 변환하거나 삭제
- tar : 여러 개의 파일을 하나의 파일로 묶거나 풀때 사용
- gzip : 압축
- base64 : 이진 데이터를 ASCII 영역의 문자들로만 이루어진 일련의 문자열로 바꾸는 인코딩 방식

<br />

## ☀️해결☀️
문제에서 모든 소문자 및 대문자는 13자리씩 회전되었다는 것을 통해 ROT13 암호 알고리즘이라는 것을 알 수 있었다.

>#### ROT13
컴퓨터로 사용되는 암호 알고리즘 가운데 가장 단순한 종류이다. 알파벳 글자를 13자리 밀어내는 것으로 만든다. 다음과 같은 테이블에 따라서 치환을 행한다. <br/>
![image](https://github.com/limhyerin/StudyNote/assets/70150896/c72ada35-226b-4413-a672-957d9d1dea79)

<br/>

먼저 파일의 형태를 확인해주었더니 ASCII로 이루어져있음을 알 수 있다.
```ssh
bandit11@bandit:~$ file data.txt
data.txt: ASCII text
```
```ssh
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
```

<br/>

ROT13 암호 알고리즘을 이용한 암호를 변환하기 위해서 tr 명령어를 사용하여 적용하면 된다.
```ssh
 $ echo "Or fher gb qevax lbhe Binygvar" | tr 'A-Za-z' 'N-ZA-Mn-za-m'
 Be sure to drink your Ovaltine
```
[출처] https://ko.m.wikipedia.org/wiki/ROT13 <br/>
```ssh
bandit11@bandit:~$ cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
```
