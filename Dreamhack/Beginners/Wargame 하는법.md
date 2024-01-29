**🌕 content 🌕** <br>
[step1 문제 접속](#Step-1-문제-접속) <br>
[step2 서버 생성하기 클릭](#Step-2-서버-생성하기-클릭) <br>
[step3 리눅스 shell에서 nc 명령어를 이용해서 접속](#Step-3-리눅스-shell에서-nc-명령어를-이용해서-접속) <br>
[Step4 DH{…} 전체를 복사해서 플래그를 제출](#Step-4-DH{…}-전체를-복사해서-플래그를-제출) <br>

<br>

### Step 1 문제 접속
<hr>
문제 사이트 주소
: https://dreamhack.io/wargame/challenges/812
![](https://velog.velcdn.com/images/hrnn00/post/d6d25df6-1f65-4083-80f7-5da52d22b0fa/image.png)

<br>

### Step 2 서버 생성하기 클릭
![](https://velog.velcdn.com/images/hrnn00/post/5468722d-d48b-473a-a52b-ffe1c03222e0/image.png)
![](https://velog.velcdn.com/images/hrnn00/post/cb9bd637-73a8-4946-8b74-ffdf8a9d5a44/image.png)

<br>

👉 **http로 접속하기**
: 브라우저에서 http://Host:Port 링크의 문제 환경에 접속. 대부분의 웹 해킹 문제는 이 방법을 사용

👉 **nc로 접속하기**
: nc Host Port 명령을 통해 문제 환경에 접속. 대부분의 포너블 문제는 이 방법을 사용

<br>

### Step 3 리눅스 shell에서 nc 명령어를 이용해서 접속
![](https://velog.velcdn.com/images/hrnn00/post/6d034e72-c2c5-4b8c-a85c-24dcf2ec4e72/image.png)

<br>

### Step 4 DH{…} 전체를 복사해서 플래그를 제출
DH{}까지 포함한 모든 문자열을 복사하여 FLAG 입력 칸에 붙여 넣고 제출하기 버튼을 클릭
![](https://velog.velcdn.com/images/hrnn00/post/87583ca5-a041-4fa0-b2f6-7d1ce6e6079c/image.png)

```
DH{d6398f06b35117877a855ade8d2015fc3b142c3ca6686ce3198e372b9ef8a644}
```

![](https://velog.velcdn.com/images/hrnn00/post/d530bb75-ab5c-422b-a9ae-d96c4b11bc6e/image.png)

문제 파일 다운로드 버튼을 클릭하면 압축 파일이 다운로드된다. 압축을 해제하면 문제를 푸는 데 필요한 소스 코드 등의 파일이 있고 문제를 분석하고 플래그를 얻기 위해서는 주어진 파일들을 잘 살펴보는 과정이 필요하다

실습 문제 파일을 다운로드하고 압축을 해제하면 C 파일 chall.c가 있다. 본 실습 문제의 코드는 단순히 플래그를 출력하는 코드이니 자세히 볼 필요가 없다. 앞으로는 자세히 봐야하니 유의하기
