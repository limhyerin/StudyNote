# 🎃 Grid 설정 🎃
다른 분의 코드를 가져와서 내코드에 적용해보는 시간을 가져보겠다! <br/>
여기서 볼 수 있듯이 grid-template-columns:4fr 6fr 부분이 주로 봐야하는 부분인데<br/>

>columns(행) : 가로 / rows(열) : 세로

columns는 가로로 40% 60% 비중을 차지하도록 설정하는 느낌으로 기억하기로 했다. rows는 세로로 설정<br/>
```css
.container {
            display:grid;
            grid-template-columns:4fr 6fr;
            grid-gap:1rem;
            background-color:lightgray;
        }
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/4e684109-cdf7-4084-acad-1ddc6435d21e)
```css
.container {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            grid-gap: 1rem;
            background-color: lightgray;
        }
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/852d8083-665c-48ca-a84a-2ae9539ffd73)
 
이 내용을 바탕으로 프로젝트에 적용을 해주었는데 우선 카드들에는 적용이 안된것같구.. 타이틀이 되는 이미지와 검색창이 창이 줄어듬과 동시에 반응형으로 길이가 창의 크기에 맞춰서 줄어드는 것을 볼 수 있다.<br/>
```css
.container {
  display: grid;
  grid-template-rows: repeat(1fr, 1fr, 8fr);
  grid-auto-columns: minmax(200px, auto);
}
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/4e650675-b209-4154-80bb-d61d02ecea01)
![image](https://github.com/limhyerin/StudyNote/assets/70150896/a6ab417e-881c-46e6-a437-cee28a4cf97d)
