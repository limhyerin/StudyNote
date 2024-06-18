# 🌳bandit8 -> bandit9🌳
> The password for the next level is stored in the file data.txt and is the only line of text that occurs only once <br/>

다음 레벨의 비밀번호는 data.txt 파일안에 들어있는데. 오직 한번만 발생되는 라인에 있는 듯 하다. <br />
중복되지 않는 줄을 찾으면 비밀번호를 찾을 수 있다. <br/>

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
     10 70LNqBAZ0bqmoYsVkZSl0Erya897os3w
     10 7Kl4tYWjanNtZxGarp8gDUA53bpncFZO
     10 8Cj6gIqYmD399yAH35r61ypOZv05J6OJ
     10 92f0fSIgFAVnutspQsJNPCoxOHAOfo5z
     10 9Aw596jhtRHzGH80UHxrcOr13vE84uKC
     10 9nDGoTE9RQMq7y3UiskVWVYWkaplocLI
     10 9yuTW4lcQqmsm6vSJHBw0rPBKlSesLu6
     10 A5z3Z3Ri86f35dqTK5NqPzGJBpikaQPY
     10 A65z6QBeywbD5tk9DldoLYeUqVOzAq0U
     10 AAB15DM9nw4GVYHsVKFz7cis1g6y5v36
     10 aGT5k9taaSyCF1FSZR0QxdjYfM1GJqoz
     10 AUHG5plJ1vmLqvZRAa82qPXns19NXogK
     10 B5D0K0WOhadIzn0pt4oxtSofq3rEzGO6
     10 bIy2XotwBoeEhEJeiNOl9aMwkwGQQgLC
     10 BqCa7xxbM7JmuOp4i3z7h8heWeXmEf8k
     10 C3waf4XycUNevWOHht9BgFi3T0g08eeZ
     10 cpQDT2cJG8BVfDQxr4AjVkAKlbXutIcM
     10 D48p3M4Hsvl5yS7VmWiLJm67w2HKaI1R
     10 dpioKGwaCK2TfoTVIBl7IQg1IwEHa84r
     10 dYfaXz4drg8JOLZNxyi7x7cV4J0ZnDIY
     10 eUg4lhfqoYBvi9qcggeuFX6xetC3gdPn
     10 F7907uXSZY3jUauSMd1md1Lz1iGzTp62
     10 GafaQz3VR90YNGUdRdVs1Ds6Kqvdsn9D
     10 gIcZTy89nvAi205mnOUEW1yFaceqzSnl
     10 h37f2K6Kb1eoD5DHcFjp4AQrv1JBOiBd
     10 haf2QmTk8J2i4qw1YCKk2zjO5M9vSroU
     10 HTdKUsLmIPFDAY2fWnjgH1h9rq6KQT7s
     10 HUWkZzQLbk1wrJYXbdkVLYLFRh9AOeaN
     10 IecInbEynGj5AVX2gXBB73Et9YdjZPnV
     10 iQVDLH0ZWQNqqK8SPw5VfaNK0rVD5HXH
     10 IrQvYnowxio071KyeDvYaMXyaV7OefCa
     10 ixaaNBAsH1oKCNMYuTz6g6CGsPA1QyVs
     10 JDrQFJQZAGwzK8e4EshwQKCCwlN8LAdK
     10 JEOLLAL8gV2Y0BEPQcAW6ZiGWhkBhof8
     10 JityyRponTVvnI1yrp5YpBCVtwUOgiL5
     10 Jj8r6Lvcv7waINhnmjSCLe0tscCgcvvN
     10 JS0ofxYYafpkWJ5VgYIykILv3R8bJYDX
     10 JzOxvhJfrUXx1hcLCEGY1tZoCvQVmqvR
     10 KJwpOsmhwq2YqIDVjh4FZPjnZwj3cd5c
     10 kS0K5Egxh7kmAfJDr09zxT6dnPpdPdDI
     10 ky8eoQAaA7EpCRfh2SkvoVhq5czkI10L
     10 L3ET2u9RyxE1GvFpfj8OtdkOodG3Q7Y0
     10 L9C4h473C4wQj5rvtONDwWgTbSSRbKer
     10 lJtdmgZINOQVcEbcQ0LJJcfI6bq86ZUM
     10 MIAB0z54ZELY7I7eU5rjl2kH0veRF31F
     10 mzFz9BsF3ZmygO5hVKlhy1PIjuWLbw3b
     10 Nh47qicCqp4PUKwb3A3QFl9eLepZJcKO
     10 nTGvE84B79luh8YregY2aPtkhKxU7gNr
     10 ObSVwH80QTEOz3VAYbuFIAc4vF8oKShi
     10 oGLA63JiVzGzQQDzDXxAd11FoVbW2J68
     10 p1SHslv0A8ByhWDtA3HPJG1uh6N6YDZH
     10 p6j0ERZrjWtOlwNlzA1Txby4MvixyYC2
     10 PiUyqIBrqmaNZtTR0Lr3Zobxb6roDOqu
     10 pOMxl399ykxAJ4a5XXWKdY6jn51qSS5e
     10 pyYax1vljH3xjM53mj53FWDO4rcXn0W7
     10 R99IuJu84mseLcdHyT7dU6p68ybO0HDL
     10 Rb8nNWWInMbltWGr5f6xIaQ192zriQSB
     10 RJGc97N2hLTgkOX1CKoYC2KkMGuSB87D
     10 rLfeZFg00Xt5MAmp68cP4O8XUWVyA30v
     10 rsv0lFiC9MFJwSv479jXsdQlHk701spj
     10 S8Udqm1CzsWnk6ILI5mAEY4ZaIiYIE92
     10 S9bKvvVWUlYlKwiNblRczTF3u1tiZ1Cf
     10 snD95f3P8ucFCa8oWFz5cbG7w4Zd5n01
     10 SPjj1nJcBaHo5AFvohxMh1QtGM73VAAF
     10 syEklKGCbn3S7OeHDOni6McV6lXcX2YQ
     10 Tc9gNkYVupWKFGMnjm8fxhD1Oc2J9UhK
     10 TlLjKsXfLuMQnBzc2pYYsMdZYKn7J5Y0
     10 U0cT5ZAZBKIuL9Ezi3MAnjiHMoSic5Qi
     10 UwwL4FMk80ju5vIcdmMFw2XoTSWjg9Pd
     10 w7pdvcGlvWj6B0wUi0T3c1Q1Jh9vF0Bu
     10 wbpUmE0ORDW3K11y6aCCO4uFb4FDIQoZ
     10 WSivv9Y7KVAsZxbU6oiC3wyVG02e99Mz
     10 WtnQEsSCYgBvJoeb9WeqSCCdAkUZSHVS
     10 XelXDhJUY6FQ50WSQL2M1c5yvqmcUDVG
     10 xlbwl4pMsBm5TipGTJ31KTtFvV6ERDDB
     10 XmCgVR6F39nrrYQFmeyffNdpvItrdvOX
     10 XO5dwgFsuPZx2sa3azbXC5iEsq0JLFIH
     10 Xs0vjf4YUyh4DrJOetfdjr1MFsAGbM3k
     10 xvhXIA0GjGafdTPkDlOFc3ICUPXhas6H
     10 y1cGBvYht0h86fNjaZKEIZzhEiJLzkAc
     10 y3lFam9pot49bjoGDMeIHO4fOZmcasev
     10 YX3D3qVjPVxBQiKudv1j4Pamk1x5oB57
     10 zDVfHceZfK7xcLFyWsVXvduhesTASqIR
     10 zFW3w9ERv5r4POTC4g9VhzIeX1ZrpajC
     10 zK2AvCjddzyRMAqxK4tvAmocgKkDa0jl
     10 zL0CIMKa1gBhF2APOPBYoWIRHxHHL9Cm
     10 zQdcHim1z3Qa5PwwIbsMXwI0rbBxij6s
     10 zsosXndKnBT21gEH6PyemPpdGpOgyQ7M
bandit8@bandit:~$
...
