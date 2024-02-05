>echo "# upload_practice" >> README.md
git init
git add README.md
git commit -m "first commit"
git branch -M main
git remote add origin https://github.com/limhyerin/upload_practice.git
git push -u origin main

# 🎃 Git 명령어 이용해서 파일 업로드 🎃
## 1. 레포지토리 생성 (Create a new repository)
레포지토리는 저장공간으로  올리고자하는 파일을 업로드하기 전에 미리 만들어주며 이름은 프로젝트나 파일에 맞게 작성해준다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/96cbde87-2f65-4040-83d0-a72fa3630983)

## 2. vscode에서 Git Bash 클릭
먼저, Visual Studio Code(VSCode)에서 코드를 작성하고 저장한 파일을 Github에 업로드 할때 맥(IOS)의 경우 터미널을 열어서 바로 진행하면 되지만 윈도우(Windows)의 경우 터미널 창을 열고 +버튼 옆에 있는 아래 꺽쇠버튼을 눌러서 Git Bash로 클릭해 준 후 사용해야 한다!
![image](https://github.com/limhyerin/StudyNote/assets/70150896/4d0fcf14-58b1-4c68-8aec-85340055565d)

## 3. 현재 위치 확인(pwd)
가장 먼저 해야할 일은 현재 위치가 업로드하고자하는 파일이 있는 위치가 맞는지 확인하는 것이다. 엉뚱한 위치에 있다면 의도치 않게 업로드할 생각이 없던 파일들이 업로드될 수 있다. 꼭 확인 필수!
![image](https://github.com/limhyerin/StudyNote/assets/70150896/d1a393c8-f5b8-43dd-9f42-ec46952c6857)

## 4. git init
코드 관리를 시작하는 명령어로, initialize (초기화하다, 초기 세팅하다)의 준말이다.
해당 명령어는 프로젝트 시작 전 딱 한 번만 입력하면 되며 정확한 프로젝트 폴더(경로)에서 입력해야 한다.
사용하기 전, 터미널에서 pwd 명령어를 통해 해당 위치를 확인하고 git init를 사용한다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/fd026a4d-3bde-484b-882c-e228dd15abff)

## 5. ls -a
ls명령어를 사용하여 현재 디렉토리에 있는 내용을 출력하는데 그중에서도 -a옵션을 활용하여 숨겨진 파일까지 확인할 수 있도록 한다. 그리고 ls -a를 통해 모든 파일을 확인하여 '.git' 가 존재하는 지 확인하면 되는데  '.git'이라는 폴더가 생기면 이때부터 코드 변경을 git에서 추적하기 시작한다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/b3d05d5f-0698-4dcd-b432-65684c50cd6f)

## 6. git add & git commit -m "메시지 작성"
git add 명령어는 저장하기 전 저장할 파일 지정하는 명령어이고 git commit -m "메시지"는 실제로 저장하는 명령어이다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/46127bd9-9df8-4c52-8771-b76a498ab656)
![image](https://github.com/limhyerin/StudyNote/assets/70150896/29f4a686-6681-4547-90df-74f1550e1529)

```bash
git add 1.html
git commit -m "회원가입 기능 작성 완료"
```

### 🤚 만약 모든 파일을 다 올리고 싶다면? 🤚

파일을 지정해서 저장하지 않고 내 프로젝트의 변경사항을 한번에 저장하기 위해서는 .(전체)를 모두 지정해서 저장한다.
```bash
git add .
git commit -m "메시지 작성"
```

## 7. git branch -M 브랜치명 (==main)
기본 브랜치는 master로 되어있는데 현재는 브랜치명(master)을 main으로 바꿔서 사용하고 있어서 main으로 해준다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/caf4012d-1167-40fb-a036-a4c3c7c688d2)

## 8. git remote add origin github 주소
![image](https://github.com/limhyerin/StudyNote/assets/70150896/93b30eba-990a-4d14-8d46-ee7612368fdc)

## 9. git push -u origin 브랜치명
추가로 수정된 코드 github에 반영하기 위해 먼저, 코드를 수정하고 저장하여 명령어를 실행한다.
>git add . & git commit -m "메시지 작성" 이 두가지 명령어를 사용하여 진행한다.
git push origin 브랜치명(ex. git branch를 통해 확인하거나 git status를 통해 branch명 확인 가능)
  
![image](https://github.com/limhyerin/StudyNote/assets/70150896/3a01e441-43aa-49d6-90ef-ef47411bf9be)

## 10. Github에서 업로드 여부 확인
![image](https://github.com/limhyerin/StudyNote/assets/70150896/3e19317e-48a9-4327-9598-e76d9d1b02cf)

### 🤚  만약 please tell me who you are이라는 문구가 뜬다면 🤚
아래와 같이 작성해주면 된다
```bash
git config user.name "유저이름"
git config user.email "이메일"
```
