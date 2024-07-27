>**🌕 content 🌕** <br>
[step1 문제 접속](#Step-1-문제-접속) <br>
[step2 서버 생성하기 클릭](#Step-2-서버-생성하기-클릭) <br>
[step3 리눅스 shell에서 nc 명령어를 이용해서 접속](#Step-3-리눅스-shell에서-nc-명령어를-이용해서-접속) <br>
[step4 DH 전체를 복사해서 플래그를 제출](#Step-4-DH-전체를-복사해서-플래그를-제출) <br>

<br>

## Step 1 문제 접속
문제 사이트 주소 : https://dreamhack.io/wargame/challenges/812 <br>

![](https://velog.velcdn.com/images/hrnn00/post/d6d25df6-1f65-4083-80f7-5da52d22b0fa/image.png)

<br>

## Step 2 서버 생성하기 클릭
![](https://velog.velcdn.com/images/hrnn00/post/5468722d-d48b-473a-a52b-ffe1c03222e0/image.png)
![](https://velog.velcdn.com/images/hrnn00/post/cb9bd637-73a8-4946-8b74-ffdf8a9d5a44/image.png)

<br>

👉 **http로 접속하기**
: 브라우저에서 http://Host:Port 링크의 문제 환경에 접속. 대부분의 웹 해킹 문제는 이 방법을 사용

👉 **nc로 접속하기**
: nc Host Port 명령을 통해 문제 환경에 접속. 대부분의 포너블 문제는 이 방법을 사용

<br>

## Step 3 리눅스 shell에서 nc 명령어를 이용해서 접속
![](https://velog.velcdn.com/images/hrnn00/post/6d034e72-c2c5-4b8c-a85c-24dcf2ec4e72/image.png)

<br>

## Step 4 DH 전체를 복사해서 플래그를 제출
DH{…} 전체를 복사해서 플래그를 제출 <br/>
DH{}까지 포함한 모든 문자열을 복사하여 FLAG 입력 칸에 붙여 넣고 제출하기 버튼을 클릭
![](https://velog.velcdn.com/images/hrnn00/post/87583ca5-a041-4fa0-b2f6-7d1ce6e6079c/image.png)

```
DH{d6398f06b35117877a855ade8d2015fc3b142c3ca6686ce3198e372b9ef8a644}
```
