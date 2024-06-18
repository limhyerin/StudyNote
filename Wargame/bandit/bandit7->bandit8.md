# 🌳bandit7 -> bandit8🌳
> The password for the next level is stored in the file data.txt next to the word millionth <br/>

다음 레벨의 비밀번호는 data.txt 파일안에 들어있는데. millionth 단어 옆에 있다고 한다. 그러면 특정 문자열을 찾는 명령어를 사용하여 찾으면 쉽게 찾을 수 있을 것 같다. <br />

<br/>

**hint commands**
>man, grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd

- grep : 파일 내 특정 문자열 검색

<br />

## ☀️해결☀️
### 01 ls -l 명령어 사용 : 파일 확인
👉 ls -l 명령어를 통해 현재 위치에 있는 data.txt 파일을 확인한다.<br/>
```ssh
bandit7@bandit:~$ ls -l
total 4088
-rw-r----- 1 bandit8 bandit7 4184396 Jun 16 02:48 data.txt
bandit7@bandit:~$
```

<br/>

### 02 cat 명령어 사용 : data.txt 파일 내용 확인
💡 data 파일 내부 내용을 확인하는데 엄청나게 많은 데이터들이 있기때문에 일일히 찾을 수 없다.<br/>
```ssh
bandit7@bandit:~$ cat data.txt
sleepiness's    jMvD0h8sijbmOaa7m6zpRBUEJJnXxXSF
peccadilloes    tdPL3xm59lQuYdptKZYOgo9LU0AE7WKM
registrations   adkkmx80PRJIgwELqji2dSrx8zGxcoGW
barefooted      Cr5p7x3QiwTvEH6Vf3DTp1VNl6kK9hXV
considerable    j5vdoYeblgWAJs8X1V4l2Ai68QEOnQui
Zapata  yK89VOdP2v6WSHhxnOJt3OOsrw1NmOJW
soupier WXZnHU8GdLMCFzYKButnkLvkNnSW0VR3
arpeggio        JtzmHA8pYEXPTkz9XKPLRWvYhUzM2eZ8
neighbors       VjwxoX0qRhxrPZOPoI94sZctel7JUhWt
Weiss   8Eoh5nWNAy2qxcRDssIY7FveDDtuMYjO
cosmology       QG51teHf7ZyYhcp5e38DOdIAQqW3UoRe
rotaries        pQ7YrZuh0kA35ylOznHX2bqvHwDR3I4E
tutorial        GwOlZgJpvSxQQW2KBzss6dzqB0F2lDAr
clipboards      DU1kgEAmMwZYDpoLEr5BCebbtpridksE
Tide's  UtdhwfshhaP1fWcl93ZpeFfd921oI8mT
immigrate       nw9pPAN1HC1tThrL886Nf6OpMqUE2tlN
skywriters      oadlVoFnKFO43D6WGTjW3MtcoekSIP3d
frillier        C8NOdI0sVylmdcSkTtJOLX1o28wGoRxo
fiber's kgAZcUDzj0212EQ4t6RLVfUJnxq553V6
palpitate       Z9MjBtZmENCHMeK8NzKGnHIBO5AtBswA
garage  JBDHgJnbjwCho6aeXJcwoLmJyiBr6ERV
...
```

### grep 명령어 : 특정 문자열(millionth) 찾기
#### 🛠️grep 옵션🛠️
|명령어|뜻|
|------|---|
|-c|일치하는 행의 수를 출력한다|
|-i|대소문자를 구별하지 않는다|
|-v|일치하지 않는 행만 출력한다|
|-n|포함된 행의 번호를 함께 출력한다|
|-l|패턴이 포함된 파일의 이름을 출력한다|
|-w|단어와 일치하는 행만 출력한다|
|-x|라인과 일치하는 행만 출력한다|
|-r|하위 디렉토리를 포함한 모든 파일에서 검색한다|
|-m 숫자|최대로 표시될 수 있는 결과를 제한한다|
|-E|찾을 패턴을 정규 표현식으로 찾는다|
|-F|찾을 패턴을 문자열로 찾는다|

[출처] https://coding-factory.tistory.com/802

<br/>

💡grep 명령어를 사용해서 data.txt 파일안에 millionth 문자열을 찾고 그 옆에 있는 password를 찾는다
```ssh
bandit7@bandit:~$ cat data.txt | grep millionth
millionth       dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc
```
