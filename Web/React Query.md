# React Query
다른 서버와의 API 통신과 비동신 데이터 관리를 위해 Redux-thunk, Redux-Saga 등 미들웨어를 채택해서 사용할 수 있었다. 그런데 문제가 있었음

<br/>

## 문제점
1. 보일러 플레이트 : 코드량이 너무 많음 <br/>
2. 규격화 문제 : Redux가 비동기 데이터 관리를 위한 전문 라이브러리가 아님<br/>

<br/>

## 리액트 쿼리 장점
1. 너무 쉽고 책임에서 자유로움 <br/>
2. 보일러 플레이트 만들다가 오류가 날 일이 없다 <br/>
3. 내가 만든 부분이 아니기에 내 잘못 아님 <br/>
4. 사용방법이 thunk에 비해 쉽고 직관적 <br/>

<br/>
<hr/>

## react query 설치
```
yarn add react-query
```

<br/>

## db.json에 저장된 값 가져오기
### db.json 작성 - db.json
```
{
  "todos": [
    {
      "id": 1,
      "title": "할일1",
      "contents": "리액트 공부",
      "isDone": false
    },
    {
      "id": 2,
      "title": "할일2",
      "contents": "스프링 공부",
      "isDone": true
    },
    {
      "id": 3,
      "title": "할일3",
      "contents": "리덕스 공부",
      "isDone": false
    }
  ]
}
```

<br/>

### db.json 로컬호스트 포트 변수에 저장해주고 사용하기
![image](https://github.com/limhyerin/StudyNote/assets/70150896/f38f4621-3a61-45dd-8da7-2a6e0b22b9b9)

<br/>

### App.jsx
```js
import React from "react";
import Router from "./shared/Router";
import { QueryClient, QueryClientProvider } from "react-query";

const queryClient = new QueryClient();
const App = () => {
  return (
    <QueryClientProvider client={queryClient}>
      <Router />
    </QueryClientProvider>
  );
};

export default App;
```

<br/>

### todos.js
잘 불러와지는지 확인하기 위해서 console 찍어봄
```
// axios 요청이 들어가는 모든 모듈
import axios from "axios";

const getTodos = async () => {
  const response = await axios.get(`${process.env.REACT_APP_SERVER_URL}/todos`);
  console.log(response);
  return response;
};

export { getTodos };
```

![image](https://github.com/limhyerin/StudyNote/assets/70150896/c4d34f44-c86b-4719-bce3-faf6e2db060a)

TodoList.jsx
useQuery를 이용하면 isLoading, isError, data 기능을 사용할 수 있는데
```
const {isLoading, isError, data} = useQuery("todos", getTodos);

  if(isLoading) {
    return <h1>로딩중입니다...</h1>;
  }

  if(isError) {
    return <h1>오류가 발생했습니다</h1>;
  }
```

<br/>

### 여기서 data를 가져올때 안가져와지면 data.data를 해줘본다
```
import React from "react";
import { StyledDiv, StyledTodoListHeader, StyledTodoListBox } from "./styles";
import Todo from "../Todo";
import { getTodos } from "../../../api/todos";
import { useQuery } from "react-query";

function TodoList({ isActive }) {
  const {isLoading, isError, data} = useQuery("todos", getTodos);

  if(isLoading) {
    return <h1>로딩중입니다...</h1>;
  }

  if(isError) {
    return <h1>오류가 발생했습니다</h1>;
  }
  return (
    <StyledDiv>
      <StyledTodoListHeader>
        {isActive ? "해야 할 일 ⛱" : "완료한 일 ✅"}
      </StyledTodoListHeader>
      <StyledTodoListBox>
        {data.data
          .filter((item) => item.isDone === !isActive)
          .map((item) => {
            return <Todo key={item.id} todo={item} isActive={isActive} />;
          })}
      </StyledTodoListBox>
    </StyledDiv>
  );
}

export default TodoList;
```

<br/>

### 값을 가져오고 추가 및 삭제 기능 추가 - todos.js
```
// axios 요청이 들어가는 모든 모듈
import axios from "axios";

const getTodos = async () => {
  const response = await axios.get(`${process.env.REACT_APP_SERVER_URL}/todos`);
  console.log(response);
  return response;
};

// 추가
const addTodo = async (newTodo) => {
  await axios.post(`${process.env.REACT_APP_SERVER_URL}/todos`, newTodo);
};

export { getTodos, addTodo };
```

<br/>

### input.jsx
import addTodo와 dispatch(addTodo(newTodo)); 각각 변경해준다
#### 수정 전
```
import { addTodo } from "../../modules/todos";
```
#### 수정 후
```
import { addTodo } from "../../../api/todos";
```

<br/>

#### 수정 전
```
// todo를 추가하는 reducer 호출
// 인자 : payload
dispatch(addTodo(newTodo));
```
#### 수정 후
리액트 관련 코드를 작성해주고
```
// 리액트 뭐리 관련 코드
  const queryClient = useQueryClient();
  const mutation = useMutation(addTodo, {
    onSuccess: () => {
      queryClient.invalidateQueries("");
      console.log('성공하였습니다');
    }
  })
```
dispatch(addTodo(newTodo)); 대신 mutation 사용
```
mutation.mutate(newTodo);
```

<br/>

### 근데 문제가 있다. 데이터를 추가하고 새로고침을 해야 추가된 내용이 적용된다 이를 위해서
queryClient.invalidateQueries를 사용해서 todos를 가져와서 적용시키면 된다
![image](https://github.com/limhyerin/StudyNote/assets/70150896/9e38792c-fbf0-4c50-9d98-5a4aaae6027c)

```
// 리액트 뭐리 관련 코드
  const queryClient = useQueryClient();
  const mutation = useMutation(addTodo, {
    onSuccess: () => {
      queryClient.invalidateQueries("todos");
      console.log('성공하였습니다');
    }
  })
```
