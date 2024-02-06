# 🎃 01 DOM 계층 구조 🎃
DOM에서 Node는 웹페이지를 구성하는 모든 HTML 태그와 텍스트, 그리고 속성 등을 하나의 블록으로 취급하는 것으로 서로 계층 구조로 연결되어 있으며, 각 블록은 자식 노드, 부모 노드, 형제 노드와 관계를 가지고 있다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/ddc4328a-4f89-4f58-911a-f5803982334e)

<br/>

# 🎃 02 Node 객체의 속성과 메소드 🎃
>getElementById("demo") : 메소드 , innerHTML : 속성
```js
document.getElementById("demo").innerHTML = "Hello World!";
```
- 속성 : 값을 가지고 있음, 해당 객체의 특성을 나타내는 값을 가져오거나 설정하는데 사용
- 메소드 : 동작을 수행함, 해당 객체가 수행하는 작업을 나타내는 함수

<br/>
 
# 🎃 03 콘솔에서 자식노드/ 부모노드 접근할때 🎃
```js
// <ul id="test">
document.getElementById("test");

document.querySelector("#test").children[0]; // 이런식으로 콘솔에서 자식 노드 접근 가능
document.querySelector("#test").children[1];
document.querySelector("#test").children[2];

document.querySelector("#test").parentElement; // 부모 노드에 접근
``` 

<br/>

# 🎃 04 만약 여러개인 태그에 접근할때 🎃
```js
document.getElementByTagName("Li"); // X
document.getElementsByTagName("Li"); // O
``` 

ul 태그의 자식 노드 중 인덱스 1번째에 있는 글자를 변경하고 싶을때

>innerText : 텍스트에 접근 가능(변경O)
```js
document.querySelector('ul').children[1].innerText="변경내용"
``` 

<br/> 

# 🎃 05 지난번에 작성해뒀던 페이지에서 DOM 접근 및 제어해보기 🎃
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <nav>
        <ul>
            <li>첫번째 메뉴</li>
            <li>두번째 메뉴</li>
            <li>세번째 메뉴</li>
        </ul>
    </nav>
    <main>
        <h1>메인 영역의 제목입니다.</h1>
        <img src="https://search.pstatic.net/common/?src=http%3A%2F%2Fblogfiles.naver.net%2FMjAxNzAxMDdfMjA0%2FMDAxNDgzNzg3NjM2MjIz.h4nyPBHWeCjOzYPvzUQL1EPUP86y6c_mgqYKcM037X4g.cgLTciL3ulg0X5phOxvoj29Vx4YL7P-1oGgtpe_i7Ssg.JPEG.tjwls1624%2Fs0NLbMFJT3.jpg&type=sc960_832"
        alt="이미지 없음"/>
    </main>
    <footer>copyright.</footer>
</html>
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/84ff178d-1f82-4356-a670-88eee8c81be2)
각각의 영역을 수정하는 것을 해볼 것인데, document.querySelector를 사용해서 ul태그의 자식 노드 0번째를 수정해보기도하고 h1 태그의 글자를 수정해보는식으로 접근하고 수정이 가능한 것을 볼 수 있다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/ae8123ca-e741-4048-8aad-91387c6a4762)
![image](https://github.com/limhyerin/StudyNote/assets/70150896/cb68a06e-e479-40be-8f54-6ce3bcd0198e)

 


