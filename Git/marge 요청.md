# 🎃 Github에서 Pull Requests(PR) 🎃
한마디로 marge를 해도되는지 요청하는 것이라고 보면된다. <br/>
![image](https://github.com/limhyerin/StudyNote/assets/70150896/e706aea1-325a-459b-a222-615b4c6d15d4)
 
<br/>

브랜치를 따로 생성해서 login 브랜치에서 코드를 수정하고 그것을 git에 push하면 login 브랜치에서만 코드가 변해있을뿐 다른 브랜치인 main이나 dev 브랜치에 적용이 되지 않는다. 그래서 변경한 login브랜치를 merge해주어서 main에 합쳐주는 작업을 해야한다.<br/>
```bash
git switch login // login 브랜치로 이동
git push origin login
``` 
그래서 그 다음 브랜치를 합쳐주는 merge 명령어를 사용해서 최종 브랜치에 합칠 브랜치를 입력해서 하는 식으로 진행을 하면되는데 브랜치를 합치는 명령어인 git merge를 잘 안쓰는 편이라고 한다.<br/>
```bash
git switch 최종 브랜치명 // git switch main)
git merge 합칠 브랜치명 // git merge login)
``` 
대신 github에서 합치는 경우가 많은데 이유는 아무래도 직관적으로 한눈에 잘보이고 다른 사람들과 다같이 인터넷상에서 코드 리뷰를 하기 위해서 그런 경우가 많다고 한다.

<br/> 

## 1) 새로운 브랜치에서 코드 수정, add-commit 해주기
```bash
git add.
git commit -m “저장 메세지”
``` 

<br/> 

## 2) git push
```bash
git push origin 수정한 코드가 있는 브랜치명
``` 
그러면 이런 노란 박스가 생기고 compare & pull request 버튼을 클릭한다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/43e3b909-ea07-42e6-aff1-a3a356c5f82a)

<br/>

## 3) 변경 세부사항 작성
그다음 리뷰어를 선택할 수도 있고 create pull request 클릭
![image](https://github.com/limhyerin/StudyNote/assets/70150896/6898758a-504a-4776-88c2-45ba457f4e02)

<br/>

## 4) 코드리뷰 / merge 완료 
코드 리뷰가 가능하고 Merge pull request 버튼을 클릭하면 merge가 완료된다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/b77bb26c-3858-4755-8aac-0a086ff46151)
merge가 완료되면 보라색창으로 변하고 완료
![image](https://github.com/limhyerin/StudyNote/assets/70150896/00bd330f-8b6c-4d9c-80de-4a588aee3c2a)

