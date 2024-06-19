# 🌳bandit10 -> bandit11🌳
> The password for the next level is stored in the file data.txt, which contains base64 encoded data <br/>

다음 레벨의 비밀번호는 base64로 인코딩된 데이터가 포함된 data.txt 파일에 저장됩니다. <br />

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
|옵션|설명|
|------|---|
|(옵션없음)|base64 언코드|
|-d|base64 디코드|
|-i|디코딩할 때, 알파벳 아닌 문자 무시|
|-w|COLS 문자 뒤에 줄 바꿈|

<br />

## ☀️해결☀️
먼저, data.txt 파일의 내용을 확인해보았더니 base64로 인코딩된 데이터가 포함되어 알 수 없는 문자들만 보이는 것을 확인할 수 있었다. 
```ssh
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
```

base64 인코딩되어 있는 데이터를 디코드 해주기 위해서 리눅스 명령어인 base64와 옵션으로 -d를 사용하여 풀어주었다
```ssh
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
```
