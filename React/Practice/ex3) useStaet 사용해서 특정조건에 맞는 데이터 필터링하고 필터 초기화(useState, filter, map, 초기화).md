>**🙉구현 사항 목록🙉** <br>
**step 1** filterByAge 함수는 최소 나이를 매개변수로 받아 해당 나이 이상인 학생들로 필터링 <br>
**step 2** filterByGrade 함수는 특정 학점을 매개변수로 받아 해당 학점의 학생들로 필터링 <br>
**step 3** resetFilter 함수는 필터를 초기화하여 모든 학생들을 표시 <br>

<br>

## 전체코드
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
  const [filteredStudents, setFilteredStudents] = useState(students);

  // TODO: filterByAge 함수를 작성하세요. 이 함수는 최소 나이를 매개변수로 받아 해당 나이 이상인 학생들로 필터링해야 합니다.
  const filterByAge = (minAge) => {
    const filtered = students.filter((student) => student.age >= minAge);
    setFilteredStudents(filtered);
  };

  // TODO: filterByGrade 함수를 작성하세요. 이 함수는 특정 학점을 매개변수로 받아 해당 학점의 학생들로 필터링해야 합니다.
  const filterByGrade = (grade) => {
    // 여기에 코드를 작성하세요.
    const filtered = students.filter((student) => student.grade === grade);
    setFilteredStudents(filtered);
  };

  // TODO: resetFilter 함수를 작성하세요. 이 함수는 필터를 초기화하여 모든 학생들을 표시해야 합니다.
  const resetFilter = () => {
    // 여기에 코드를 작성하세요.
    setFilteredStudents(students);
  };

  return (
    <div>
      <h1>학생 목록</h1>
      <button onClick={() => filterByAge(24)}>24세 이상</button>
      <button onClick={() => filterByGrade("A")}>A등급</button>
      <button onClick={resetFilter}>필터 초기화</button>
      <ul>
        {filteredStudents.map((student, index) => (
          <li key={index}>
            {student.name} - Age: {student.age}, Grade: {student.grade}
          </li>
        ))}
      </ul>
    </div>
  );
}

export default App;

```
<br>

## 01 filterByAge 함수는 최소 나이를 매개변수로 받아 해당 나이 이상인 학생들로 필터링
![](https://velog.velcdn.com/images/hrnn00/post/84c1da5c-c822-47f4-a7eb-bcda7b4b35f4/image.png)

```js
const filterByAge = (minAge) => {
	// 여기에 코드를 작성하세요.
    const filtered = filteredStudents.filter((student) => student.age >= minAge);
    setFilteredStudents(filtered);
};
```
<br>

## 02 filterByGrade 함수는 특정 학점을 매개변수로 받아 해당 학점의 학생들로 필터링
![](https://velog.velcdn.com/images/hrnn00/post/d585e8fb-7457-4c20-b308-8c7e70eeb3b7/image.png)

```js
const filterByGrade = (grade) => {
	// 여기에 코드를 작성하세요.
    const filtered = filteredStudents.filter((student) => student.grade === grade);
    setFilteredStudents(filtered);
};
```
<br>

## 03 resetFilter 함수는 필터를 초기화하여 모든 학생들을 표시
![](https://velog.velcdn.com/images/hrnn00/post/9a95135f-2bb7-4154-9e44-8aead0f26478/image.png)

```js
const resetFilter = () => {
	// 여기에 코드를 작성하세요.
    setFilteredStudents(initialState);
};
```

초기화하기 위해 전체배열 변수에 저장해두기
```js
const initialState = [
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
```
