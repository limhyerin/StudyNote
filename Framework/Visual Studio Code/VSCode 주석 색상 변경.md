# 🎃 VSCode 주석 색상 변경 🎃
VSCode를 사용하다가 테마를 변경하다보니 이것저것 눈에 보이는 것들을 조금 변경시켜보고 싶었다. <br/>
그러다가 주석색상을 변경하는 방법을 알게 되어서 정리 <br/>

<br/>
  
>파일 -> 설정 -> 버튼 클릭

<br/>

![image](https://github.com/limhyerin/StudyNote/assets/70150896/4bf980da-931e-4432-84ea-264b01780640)
 
그러면 settings.json 파일이 나오게 되고 괄호 안에 해당하는 코드를 넣어주면 된다.

![image](https://github.com/limhyerin/StudyNote/assets/70150896/fd7278a6-b8fd-4118-bb2b-beb7606d4212)

```json
// 주석 코드 색상 변경
"editor.tokenColorCustomizations": {
    "comments": "색상코드입력" //"#828dc093"
},
```
