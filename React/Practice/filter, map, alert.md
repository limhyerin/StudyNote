>**문제 구현 사항** <br>
**step 1** filter를 사용해서 18세 이상의 학생들만 선택하기 <br>
**step 2** map을 사용해서 filteredStudents를 랜더링하기 <br>
**step 3** 학생이름을 클릭하면 나이와 점수가 alert되도록 하기 <br>

### 전체 코드

```js
import React from "react";

function App() {
  const students = [
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
  ];

  // TODO: filter를 사용하여 18세 이상의 학생들만 선택하세요.
  const filteredStudents = students.filter((student) => student.age >= 18);

  return (
    <div>
      <h1>학생 목록</h1>
      <ul>
        {/* TODO: map을 사용해서 filteredStudents를 여기에 렌더링하세요. */}
        {/* TODO: 학생이름을 클릭하면 나이와 점수가 alert 돼야 해요.*/}
        {filteredStudents.map((student, index) => {
          return (
            <ul onClick={()=> {
              alert(`나이는 ${student.age}살이고 점수는 ${student.grade}입니다.`);
            }} key={index}>
            name : {student.name}
            </ul>
          )
        })}
      </ul>
    </div>
  );
}

export default App;


```

<hr>
<br>

### 01 filter를 사용해서 18세 이상의 학생들만 선택하기
![](https://velog.velcdn.com/images/hrnn00/post/966813f5-2984-4100-a301-f2cc4722f5cb/image.png)
#### 1) 화살표 함수 이용
```js
const filteredStudents = students.filter((student) => student.age >= 18);
```
#### 2) function 함수 이용
```js
const filteredStudents = students.filter(function(student){
    return student.age >= 18;
})
```

<br>

### 02 map을 사용해서 filteredStudents를 랜더링하기
![](https://velog.velcdn.com/images/hrnn00/post/ce2779cb-1b7b-4157-a18a-02a19d7f74ce/image.png)
#### 1) 화살표 함수 이용

```js
filteredStudents.map((student, index) => {
	return (
		<ul onClick={()=> {
			alert(`나이는 ${student.age}살이고 점수는 ${student.grade}입니다.`);
		}} key={index}>
            name : {student.name}
        </ul>
    )
})
```
#### 2) function 함수 이용
```js
filteredStudents.map(function(student, index) {
    return (
		<ul onClick={() => } key={index}>
			name : {student.name}
		</ul>
   	)
})
```

<br>

### 03 학생이름을 클릭하면 나이와 점수가 alert되도록 하기
```html
<ul onClick={() => } key={index}>
    name : {student.name}
</ul>
```
