# 🌕 contents 🌕
>01 협업 초기 세팅<br/>
02 Github 첫 업로드 순서<br/>
03 Github에 추가적으로 업로드 순서<br/>
04 브랜치 생성 이동<br/>
05 다른 팀원의 변경한 코드 가져오는 순서<br/>
06 코드 리뷰 요청하는 방법<br/>

<br/>

## 01 협업 초기 세팅
### 🙉 팀장 혹은 담당자 역할 🙉
 1) Github에서 레포지토리 생성
 2) 초기 코드 작성 후 업로드
 3) 브랜치 생성(dev)
 4) Github에서 Settings - General - dev 브랜치 default 설정
 5) 팀원들 collaborator로 등록

<br/> 

### 🐶 팀원들 역할 🐶
#### 1) 알림을 확인해서 해당 레포지토리의 collaborator 등록 수락
![image](https://github.com/limhyerin/StudyNote/assets/70150896/68a4303c-d107-498d-8276-118051357e17)
 
#### 2) git 사이트 복사
![image](https://github.com/limhyerin/StudyNote/assets/70150896/602e57e4-ce3b-46e9-a2ea-4be58cc0ba08)


#### 3) git clone 깃허브 주소 . 
```bash
git clone https://github.com/hyun0Zin/git-test.git .
```

>**git 사이트 복사**
리뷰요청 -> 리뷰하는 사람은 코드에서 +버튼 누르고 코멘트해서 보냄+finish를 눌러서 approve(승인) / request changes(바꾸세요) / comment(약간 애매하고 코멘트를 할때)

![image](https://github.com/limhyerin/StudyNote/assets/70150896/580eaf1d-c75e-4a63-b716-c553a8022a04)

## 02 Github 첫 업로드 순서
### 1) git init
### 2) pwd, ls -a
### 3) git add 파일명(or .) & git commit -m "메시지 작성"
### 4) git branch -M 브랜치명 (==main)
### 5) git remote add origin github 주소
### 6) git push -u origin 브랜치명

<br/> 

## 03 Github에 추가적으로 업로드 순서
수정한 파일이 있는 브랜치 부분에서 시작
### 1) git add 파일명(or .) & git commit -m "메시지 작성"
### 2) 변경한 파일 push하는 두가지 경우
  - git push -u origin 브랜치명 : 그냥 해당 브랜치명에만 올릴때
  - git push origin 브랜치명 : 다른 default 브랜치에 합칠때
### 3) Github에서 Pull Request 들어가기
### 4) New pull request 를 눌러서 compare을 내가 수정해서 push한 브랜치로 해줌
![image](https://github.com/limhyerin/StudyNote/assets/70150896/5f1631f4-6428-4545-8ddc-1bee90f9d84c)

<br/> 

## 04 브랜치 생성 이동
### 1) git branch 브랜치명 : 브랜치 생성
![image](https://github.com/limhyerin/StudyNote/assets/70150896/c0d205b2-c9bc-4746-a81c-296b92dcbda9)
### 2) git branch : 브랜치 확인
### 3) git switch 브랜치명 : 브랜치 이동
![image](https://github.com/limhyerin/StudyNote/assets/70150896/3d2d1e51-fcdc-4bc3-a003-1fe8653b6dcf)
![image](https://github.com/limhyerin/StudyNote/assets/70150896/2bd7af69-0ca9-42c9-b349-82328ae27df6)
### 4) git switch -c 브랜치명 : 브랜치 생성 + 이동을 한번에
### 5) git push origin 브랜치명 : 생성한 브랜치에서 수정한 내용 올리기
![image](https://github.com/limhyerin/StudyNote/assets/70150896/94171607-66d4-4a43-8ef5-7e1d61672335)

<br/>

## 05 다른 팀원의 변경한 코드 가져오는 순서
### 1) git switch main
>comment : 본인의 로컬 pc니까 dev 브랜치에 변경된 코드를 불러와도 괜찮은건지?? <br/>
본인의 기능 브랜치에 코드를 가져오는게 좋나?<br/>

### 2) git pull origin main
![image](https://github.com/limhyerin/StudyNote/assets/70150896/305a4dee-107e-4a69-860a-d08bdba5b8ae)

<br/> 

## 06 코드 리뷰 요청하는 방법
리뷰요청 -> 리뷰하는 사람은 코드에서 +버튼 누르고 코멘트해서 보냄+finish를 눌러서
>approve(승인) / request changes(바꾸세요) / comment(약간 애매하고 코멘트를 할때)

![image](https://github.com/limhyerin/StudyNote/assets/70150896/e6dc25da-28f9-48b1-8cf3-a491849be8ae)
![image](https://github.com/limhyerin/StudyNote/assets/70150896/605a4d20-69f8-4276-ae3b-807ccc981e33)
![image](https://github.com/limhyerin/StudyNote/assets/70150896/9aaf085b-63c1-4f37-a582-9bf004666359)
![image](https://github.com/limhyerin/StudyNote/assets/70150896/55e666c6-79a3-493f-bac7-0250cb3f6f0d)






