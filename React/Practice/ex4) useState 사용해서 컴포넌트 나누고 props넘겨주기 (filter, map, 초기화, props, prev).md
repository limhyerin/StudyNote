> **🙉구현 세부 사항🙉** <br>
**step 1** App.js : 전체 틀, props 넘겨주기 <br>
**step 2** filterButtons.js : 각 버튼에 해당하는 값 filter, map, 초기화 <br>
**step 3** studentList.js : 전체 학생들 이름 리스트 출력 <br>


## 구현 화면
![](https://velog.velcdn.com/images/hrnn00/post/e23323d2-93c2-4d00-aacc-8910754f72c2/image.png)

<br>

## 전체 코드

```js
// App.js
import React, { useState } from "react";
import FilterButtons from "./components/FilterButtons";
import StudentList from "./components/StudentList";

function App() {
  const initialStudents = [
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
  ];

  const [filteredStudents, setFilteredStudents] = useState(initialStudents);

  return (
    <div>
      <h1>학생 목록</h1>
      <FilterButtons
      setFilteredStudents={setFilteredStudents}
      initialStudents={initialStudents}
      />
      <StudentList
      filteredStudents={filteredStudents}
      />
    </div>
  );
}

export default App;

```

```js
// filterButtons.js
import React from "react";

function FilterButtons({setFilteredStudents, initialStudents}) {
  const filterByAge = (minAge) => {
    setFilteredStudents(function(prev) {
      return prev.filter((student) => student.age >= minAge)
    });
    // setFilteredStudents((prev) => 
    // prev.filter((student) => student.age >= minAge));
  };

  const filterByGrade = (grade) => {
    setFilteredStudents(function(prev) {
      return prev.filter((student) => student.grade === grade)
    });
  };
  
  const resetFilter = () => {
    setFilteredStudents(initialStudents);
  };

  return (
    <div>
      <button onClick={() => filterByAge(18)}>18세 이상</button>
      <button onClick={() => filterByGrade("A")}>A등급</button>
      <button onClick={resetFilter}>필터 초기화</button>
    </div>
  );
}

export default FilterButtons;

```

```js
// studentList.js
import React from "react";

// TODO: StudentList 컴포넌트를 작성하세요. props로 학생 목록을 받아와서 표시해야 합니다.
// props로 데이터 받아와서 리스트 목록 보여주는
function StudentList({filteredStudents}) {
  return (
    <ul>
      {
        filteredStudents.map((student, index) => (
          <li key={index}>
            {student.name}
          </li>
        ))}
    </ul>
  );
}

export default StudentList;

```

<br>

## 01 App.js : 전체 틀, props 넘겨주기
![](https://velog.velcdn.com/images/hrnn00/post/2a30f4d7-60e9-4070-9189-7595c5bab4fd/image.png)

```js
const initialStudents = [
    { name: "Alice", age: 17, grade: "A" },
    { name: "Bob", age: 18, grade: "B" },
    { name: "Charlie", age: 16, grade: "C" },
    { name: "Diana", age: 19, grade: "D" },
  ];

  const [filteredStudents, setFilteredStudents] = useState(initialStudents);

  return (
    <div>
      <h1>학생 목록</h1>
      {/* TODO: FilterButtons 컴포넌트를 작성하고 필요한 props를 전달하세요. */}

      <FilterButtons
      /* 필요한 props를 여기에 전달하세요. */
      setFilteredStudents={setFilteredStudents}
      initialStudents={initialStudents}
      />

      {/* TODO: StudentList 컴포넌트를 작성하고 필요한 props를 전달하세요. */}
      <StudentList
      /* 필요한 props를 여기에 전달하세요. */
      filteredStudents={filteredStudents}
      />
    </div>
  );
```
<br>

## 02 filterButtons.js : 각 버튼에 해당하는 값 filter, map, 초기화
![](https://velog.velcdn.com/images/hrnn00/post/4a0e9ac9-6227-4561-b1d5-e9f44e92fc5f/image.png)

prev : useState의 이전값
### 1) 화살표 함수 이용
```js
const filterByAge = (minAge) => {
    setFilteredStudents(function(prev) {
      return prev.filter((student) => student.age >= minAge)
    });
  };
```
### 2) function 함수 이용
```js
const filterByAge = (minAge) => {
    setFilteredStudents((prev) => 
    prev.filter((student) => student.age >= minAge));
  };
```
### 3) onClick 인자받기
받을 인자가 없을 땐 중괄호 안에 바로 작성해줘도 됌
```js
return (
    <div>
      {/* 여기에 필터링 버튼들을 완성하세요. */}
      {/*받을 인자가 없을땐 중괄호 안에 그냥 작성하고 받을 인자가 있으면 화살표함수 사용해서 작성*/}
      <button onClick={() => filterByAge(18)}>18세 이상</button>
      <button onClick={() => filterByGrade("A")}>A등급</button>
      <button onClick={resetFilter}>필터 초기화</button>
    </div>
  );
```
<br>

## 03 studentList.js : 전체 학생들 이름 리스트 출력
![](https://velog.velcdn.com/images/hrnn00/post/e23323d2-93c2-4d00-aacc-8910754f72c2/image.png)
props로 데이터 받아와서 리스트 목록 보여주기
```js
// studentList.js
import React from "react";

// TODO: StudentList 컴포넌트를 작성하세요. props로 학생 목록을 받아와서 표시해야 합니다.
function StudentList({filteredStudents}) {
  return (
    <ul>
      {/* 여기에 학생 목록을 표시하는 로직을 작성하세요. */}
      {/* ex: 홍길동 (20세) - A등급 */}
      {
        filteredStudents.map((student, index) => (
          <li key={index}>
            {student.name} - {student.grade}등급
          </li>
        ))}
    </ul>
  );
}

export default StudentList;

```
