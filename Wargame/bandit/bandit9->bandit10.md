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
👉 ls -l 명령어를 통해 현재 위치에 있는 data.txt 파일을 확인한다.<br/>
```ssh
bandit9@bandit:~$ ls -l
total 20
-rw-r----- 1 bandit10 bandit9 19379 Jun 16 02:47 data.txt
```

<br/>

grep 명령어를 이용해서 = 문자열이 포함된 부분을 찾으려고 했는데 되지 않았다. 
```ssh
bandit9@bandit:~$ cat data.txt | grep '='
grep: (standard input): binary file matches
```
```ssh
bandit9@bandit:~$ grep '=' data.txt
grep: data.txt: binary file matches
```

<br/>

cat 명령어를 이용해서 file의 내용을 확인해보았더니 이런식으로 되어있었기 때문이었다
```ssh
L▒▒▒D%.▒▒▒+
'▒▒▒▒>▒▒▒d▒,▒\▒▒!▒▒^ZAxTG2▒▒▒>▒S/▒▒w▒▒▒O▒▒x7▒▒▒ l@▒▒`v▒Cx▒▒d9▒\▒▒Գ/▒▒$fs▒▒u+n▒M▒▒J;▒o▒▒j-▒|E:>0▒1X1\31▒▒▒/▒▒B▒ڦ,,/▒▒끀tK6▒{ܓ▒@▒J
▒▒[▒▒▒ώ▒▒▒̙zWu▒▒DR▒3϶▒hn▒▒▒V▒▒,▒6▒Frםʪ▒▒▒▒
▒Y▒▒▒dC▒▒▒ź8▒▒'䷹▒>'▒.&▒▒,s~Јߓ:▒?▒j▒▒▒▒cN▒
                                         ▒▒q▒▒▒?:|`▒▒ن
W▒r5▒▒▒▒bQ{?▒▒▒▒▒^▒%~U▒v▒▒?▒A▒7▒▒1▒▒S,Ā▒7▒ڸ▒▒▒98I▒▒zZ?▒sz▒h&▒▒7▒▒▒▒܌2▒_N▒▒!▒▒▒A▒~▒▒ԑ3   0▒s|:▒▒c▒3▒Z▒▒w8▒%O▒9▒▒▒=▒<▒3▒=▒▒▒ɲ▒SW▒>q▒Y▒▒m▒▒.▒múÜ▒(▒s▒Fk▒f▒▒t▒K▒▒▒Ǌ[dy▒x▒▒▒r▒▒▒▒Yog▒▒▒▒sq▒▒+9▒▒▒▒▒w▒
```

<br/>

strings를 이용하여 문자열만 추출하고 여러개의 =이라고 했기때문에 ==를 찾아주면 password를 찾을 수 있었다.
```ssh
bandit9@bandit:~$ strings data.txt | grep '=='
*N========== the
========== password
========== is
w========== FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
bandit9@bandit:~$
```
