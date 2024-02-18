# 🌻Thunk🌻
리덕스에서 많이 사용하고 있는 미들웨어중에 하나.<br/>
thunk를 사용하면 우리가 dispatch를 할때 객체가 아닌 함수를 dispatch 할 수 있게 해준다. 즉 dispatch(객체) 가 아니라 dispatch(함수)를 할 수 있게 되는 것
![image](https://github.com/limhyerin/StudyNote/assets/70150896/71163061-7dd9-485f-8f51-a27cff9958ed)

그래서 중간에 우리가 하고자 하는 작업을 함수를 통해 넣을 수 있고, 그것이 중간에 실행이 되는 것<br/>
thunk 함수의 역할은 “3초를 기다리는 것”. 그리고 3초가 지나면 원래 하려고 했던 ADD_NUMBER를 해주는 것 까지가 thunk함수가 해야 할 일이다<br/>

<br/>

## 🌼counter.js🌼
```js
// src/redux/modules/counterSlice.js

import { createSlice, createAsyncThunk } from "@reduxjs/toolkit";

export const __addNumber = createAsyncThunk(
	// 첫번째 인자 : action value
  "addNumber", 
	// 두번째 인자 : 콜백함수 
  (payload, thunkAPI) => {
    setTimeout(() => {
      thunkAPI.dispatch(addNumber(payload));
    }, 3000);
  }
);

const initialState = {
  number: 0,
};

const counterSlice = createSlice({
  name: "counter",
  initialState,
  reducers: {
    addNumber: (state, action) => {
      state.number = state.number + action.payload;
    },

    minusNumber: (state, action) => {
      state.number = state.number - action.payload;
    },
  },
});


export const { addNumber, minusNumber } = counterSlice.actions;
export default counterSlice.reducer;
```

<br/>

## 🌼App.jsx🌼
```js
// src/App.jsx

import React from "react";
import { useState } from "react";
import { useDispatch, useSelector } from "react-redux";
import { minusNumber, __addNumber } from "./redux/modules/counterSlice";

const App = () => {
  const dispatch = useDispatch();
  const [number, setNumber] = useState(0);
  const globalNumber = useSelector((state) => state.counter.number);

  const onChangeHandler = (evnet) => {
    const { value } = evnet.target;
    setNumber(+value);
  };

  // thunk 함수를 디스패치한다. payload는 thunk함수에 넣어주면,
  // 리덕스 모듈에서 payload로 받을 수 있다.
  const onClickAddNumberHandler = () => {
    dispatch(__addNumber(number));
  };

  const onClickMinusNumberHandler = () => {
    dispatch(minusNumber(number));
  };

  return (
    <div>
      <div>{globalNumber}</div>
      <input type="number" onChange={onChangeHandler} />
      <button onClick={onClickAddNumberHandler}>더하기</button>
      <button onClick={onClickMinusNumberHandler}>빼기</button>
    </div>
  );
};

export default App;
```
