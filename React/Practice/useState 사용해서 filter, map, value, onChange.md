>**step 1** filter를 사용하여 minAge 이상의 학생들만 선택 <br>
**step 2** map을 사용하여 필터링된 학생들의 정보를 표시 <br>
**step 3** input에 입력된 값(숫자) 이상의 나이를 가진 학생들만 출력 <br>

![](https://velog.velcdn.com/images/hrnn00/post/2f7fe539-06e0-4b6f-be6e-2f8c8a129975/image.gif)

## 전체 코드

```js
import React, { useState } from "react";

function App() {
  const students = [
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
    { name: "Elmo", age: 20, grade: "E" },
    { name: "Fiona", age: 21, grade: "F" },
    { name: "Gabe", age: 22, grade: "A" },
    { name: "Hannah", age: 23, grade: "B" },
    { name: "Irene", age: 24, grade: "C" },
    { name: "Jenny", age: 25, grade: "D" },
    { name: "Kevin", age: 26, grade: "E" },
    { name: "Linda", age: 27, grade: "F" },
  ];

  const [minAge, setMinAge] = useState(18);

  // TODO: filter를 사용하여 minAge 이상의 학생들만 선택하세요.
  const filteredStudents = students.filter((student) => student.age >= minAge);

  // TODO: map을 사용하여 필터링된 학생들의 정보를 표시하세요.
  const studentList = filteredStudents.map((student, index) => (
    <li key={index}>
      {student.name} - Age: {student.age}, Grade: {student.grade}
    </li>
  ));

  return (
    <div>
      <h1>학생 목록</h1>
      다음 나이 이상의 학생목록만 출력해요 :{" "}
      {/* TODO: input에 입력된 값(숫자) 이상의 나이를 가진 학생들만 출력하세요. */}
      <input type="number" value={minAge} onChange={(e)=> {
        setMinAge(e.target.value);
      }}/> 살 이상
      <ul>{studentList}</ul>
    </div>
  );
}

export default App;

```



## 01 filter를 사용하여 minAge 이상의 학생들만 선택
### 1) 화살표 함수 이용
```js
const [minAge, setMinAge] = useState(18);

// TODO: filter를 사용하여 minAge 이상의 학생들만 선택하세요.
const filteredStudents = students.filter((student) => student.age >= minAge);
```
### 2) function 함수 이용
```js
const [minAge, setMinAge] = useState(18);

// TODO: filter를 사용하여 minAge 이상의 학생들만 선택하세요.
const filteredStudents = students.filter(function (student) {
    return student.age >= minAge;
})
```

## 02 map을 사용하여 필터링된 학생들의 정보를 표시

```js
const studentList = filteredStudents.map((student, index) => (
    <li key={index}>
      {student.name} - Age: {student.age}, Grade: {student.grade}
    </li>
));
```
## 03 input에 입력된 값(숫자) 이상의 나이를 가진 학생들만 출력
```html
<div>
	<h1>학생 목록</h1>
	다음 나이 이상의 학생목록만 출력해요 :{" "}
	{/* TODO: input에 입력된 값(숫자) 이상의 나이를 가진 학생들만 출력하세요. */}
	<input type="number" value={minAge} onChange={(e)=> {
		setMinAge(e.target.value);
	}}/> 살 이상
	<ul>{studentList}</ul>
</div>
```
