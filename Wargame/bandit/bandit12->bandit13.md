# 🌳bandit12 -> bandit13🌳
> The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

다음 단계의 비밀번호는 반복적으로 압축된 파일의 헥스덤프인 data.txt 파일에 저장됩니다. 이 수준의 경우 /tmp 아래에 작업할 수 있는 디렉토리를 만드는 것이 유용할 수 있습니다. 추측하기 어려운 디렉토리 이름으로 mkdir를 사용하세요. 또는 더 나은, "mktemp -d" 명령을 사용하세요. 그런 다음 cp를 사용하여 데이터 파일을 복사하고 mv를 사용하여 이름을 바꾸세요 (맨페이지를 읽으세요!)<br/>
<br/>

hexdump는 컴퓨터의 저장장치에 있는 컴퓨터의 데이터를 16진법으로 표시한것

<br/>

**hint commands**
>grep, sort, uniq, strings, base64, tr, tar, gzip, bzip2, xxd, mkdir, cp, mv, file

- grep : 파일 내 특정 문자열 검색
- uniq : 중복된 내용 제거
- strings : 문자열만 추출하여 출력
- tr : 지정한 문자를 변환하거나 삭제
- tar : 여러 개의 파일을 하나의 파일로 묶거나 풀때 사용
- gzip : 압축
- base64 : 이진 데이터를 ASCII 영역의 문자들로만 이루어진 일련의 문자열로 바꾸는 인코딩 방식
- xxd : 주어진 파일이나 input으로 들어온 문자들을 16진수로 만들어줌
- cp : 파일 복사, 새로운 파일 이름(이미 동일한 파일이름이 있으면 덮어씀)
- mv : 파일이나 디렉토리 이동

<br />

## ☀️해결☀️
