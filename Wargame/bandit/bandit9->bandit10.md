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
bandit8@bandit:~$ ls -l
total 36
-rw-r----- 1 bandit9 bandit8 33033 Jun 16 02:48 data.txt
```

<br/>

### 02 cat 명령어 사용 : data.txt 파일 내용 확인
❗ data 파일 내부 내용을 확인하는데 처음에는 sort(정렬) 없이 uniq -c  명령어를 사용하여 중복횟수를 확인했었는데 그렇게 하니까 모두 다 1로 나오는 것이였다. 그래서 뭐가 문제인지 확인해보았더니 중복 확인을 하기 전에 sort(정렬)을 한번 해주고 해야 한다고 한다.<br/>
```ssh
1 JityyRponTVvnI1yrp5YpBCVtwUOgiL5
1 SPjj1nJcBaHo5AFvohxMh1QtGM73VAAF
1 JS0ofxYYafpkWJ5VgYIykILv3R8bJYDX
1 cpQDT2cJG8BVfDQxr4AjVkAKlbXutIcM
1 5RyaP1nGZEj1mJeHqle2dBz5rby63GTy
1 HUWkZzQLbk1wrJYXbdkVLYLFRh9AOeaN
1 PiUyqIBrqmaNZtTR0Lr3Zobxb6roDOqu
1 GafaQz3VR90YNGUdRdVs1Ds6Kqvdsn9D
1 A5z3Z3Ri86f35dqTK5NqPzGJBpikaQPY
1 pyYax1vljH3xjM53mj53FWDO4rcXn0W7
1 70LNqBAZ0bqmoYsVkZSl0Erya897os3w
1 xlbwl4pMsBm5TipGTJ31KTtFvV6ERDDB
1 cpQDT2cJG8BVfDQxr4AjVkAKlbXutIcM
1 eUg4lhfqoYBvi9qcggeuFX6xetC3gdPn
1 aGT5k9taaSyCF1FSZR0QxdjYfM1GJqoz
1 pyYax1vljH3xjM53mj53FWDO4rcXn0W7
1 AUHG5plJ1vmLqvZRAa82qPXns19NXogK
1 R99IuJu84mseLcdHyT7dU6p68ybO0HDL
...
```
💡data.txt 파일을 sort해준 후, 중복되는 문자열을 카운트 해주면 딱 하나 중복되지 않은 문자열이 있고 password를 찾을 수 있었다.
```ssh
bandit8@bandit:~$ cat data.txt | sort | uniq -c
     10 19E9USQggdrlHMFz9MFtETfUToTqBpWn
     10 1D4O2h1aT7IIY1BOAj6EeEhqDmb9CsMg
     10 1qEyDdyNewcZSSAGASXm1KW0VAPhR0S8
     10 25708Zap4Qz3EgSkRNkFJJwCtgk6i2ci
     10 2aPsK2zWIOOrPdkW9mKoj2I2H0HmRG9Z
     10 2kkg2dfdBVe5aKjc7E9aM19b4GkZvMh1
     10 32o6Avz8mKr8Mgp3JahSTXt8nsX8teX4
     10 44lhWq78UrXBv6EmVaIXEMk8aGtSGnPJ
     10 48xspO1WZse2xjLfC47Jf3U1TTWpP3wz
      1 4CKMh1JI91bUIZZPXDqGanal4xvAg0JM
     10 540xMfl7DTdqBhKEDV1wAGTFNJbrJIVq
     10 5RyaP1nGZEj1mJeHqle2dBz5rby63GTy
     10 61iCRNsMy64LkxA6YE1I5ZXxnphwHpqt
    ...
bandit8@bandit:~$
...
