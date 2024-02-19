# Redux-toolkit
Redux-toolkit 설치
```
npm install @reduxjs/toolkit
```
```
yarn add @reduxjs/toolkit
```

configStore.js
```js
import { createStore } from "redux";
import rootReducer from "../modules/data";

const store = createStore(rootReducer);

export default store;
```

```js
import { configureStore } from "@reduxjs/toolkit";
import data from "../modules/data";

const store = configureStore({
  reducer: {
    data: data,
  },
});

export default store;
```

modules 폴더 안에 data.js
```js
export const SET_DATA = "SET_DATA";
export const SET_SELECT_BTN = "SET_SELECT_BTN";
export const SET_SELECT_WHO = "SET_SELECT_WHO";

export const setData = (data) => ({
  type: SET_DATA,
  data,
});
export const setSelectBtn = (selectBtn) => ({
  type: SET_SELECT_BTN,
  selectBtn,
});
export const setSelectWho = (selectWho) => ({
  type: SET_SELECT_WHO,
  selectWho,
});

const initialState = {
  data: JSON.parse(localStorage.getItem(["data"])) || [],
  selectBtn: "winter",
  selectWho: "winter",
};

export default function reducer(state = initialState, action) {
  switch (action.type) {
    case SET_DATA:
      return { ...state, data: action.data };
    case SET_SELECT_BTN:
      return { ...state, selectBtn: action.selectBtn };
    case SET_SELECT_WHO:
      return { ...state, selectWho: action.selectWho };
    default:
      return state;
  }
}
```

```js
import { createSlice } from '@reduxjs/toolkit';

const initialState = {
  data: JSON.parse(localStorage.getItem(['data'])) || [],
  selectBtn: 'winter',
  selectWho: 'winter',
};

const dataSlice = createSlice({
  name: 'data',
  initialState,
  reducers: {
    setData: (state, action) => {
      state.data = action.payload;
    },
    setSelectBtn: (state, action) => {
      state.selectBtn = action.payload;
    },
    setSelectWho: (state, action) => {
      state.selectWho = action.payload;
    }
  }
});

export const { setData, setSelectBtn, setSelectWho } = dataSlice.actions;

export default dataSlice.reducer;
```
