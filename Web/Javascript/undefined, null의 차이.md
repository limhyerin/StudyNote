# 🎃 undefined, null의 차이 🎃

### 01 undefined
undefined는 값이 있어야 할  것 같은데 값이 없는 경우 자동으로 부여되는 것

- 변수에 값이 지정되지 않은 경우 <br/>
- 데이터 영역의 메모리 주소를 지정하지 않은 식별자에 접근하는 경우 <br/>
- 객체(.)나 배열([ ])로 접근하려 할 때, 해당 데이터가 존재하지 않는 경우 <br/>
- return 문이 없거나 호출되지 않는 함수를 실행하는 경우 <br/>

<br/>

값이 없다는 것을 표현할 때에는 undefined를 사용하는 것이 아닌 null값을 사용해야 한다. 
![image](https://github.com/limhyerin/StudyNote/assets/70150896/e42fab82-2e28-492e-a894-f203bdb730e3)

<br/>

### 02 null
값이 없다는 것을 표현할 때에 사용

<br/>

예제와 함께 보았을때 우선 typeof null로 나오는 부분은 자바스크립트의 버그라서 신경쓰지 않아도 된다.
동등연산자(==)는 타입까지는 같지 않아도 되기 때문에 예제에서 n==undefined/ n==null을 했을때 true로 나왔다.
그래서 일치연산자(===)를 써야 undefined와 null 구분이 확실하게 된다.

![image](https://github.com/limhyerin/StudyNote/assets/70150896/a8df36b5-f267-4a8f-89bf-7193f018bd5f)
