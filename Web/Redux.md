🌻Redux🌻
Redux 사용이유?

- props drilling 문제를 해결하기 위해서 사용

- state 변경, 관리할 때 사용



Redux에는 몸무게의 값과 조건을 걸어서 수정하거나 그럴때 방법을 정해둠

```
// index.js
import { provider } from 'react-redux';
import { createStore } from 'redux'

const 체중 = 100;

// state 수정 방법
function reducer(state = 체중, action) {
	if(action.type === "증가") {
    	state++;
        return state;
    } else if(action.type === "감소") {
    	state--;
        return state;
    } else {
    	return state
    }
}

let store = createStore(reducer);

ReactDOM.render(
	<React.StrictMode>
    	<Provider store={store}>
        	<App />
        </Provider>
    </React.StrictMode>
    document.getElementById('root')
);
```

```
// App.js
import "./App.css";
import { useSelector } from "react-redux";

function App() {
	const 꺼내온값 = useSelector((state) => state);
    
    return (
    	<div className="App">
        	<p>님의 몸무게 : {꺼내온값}</p>
        </div>
    )
}
```

```
// index.js
import React from "react";
import ReactDOM from "react-dom/client";
import "./index.css";
import RouterConfig from "./Router";
import reportWebVitals from "./reportWebVitals";
import { Provider } from "react-redux";
import store from "./redux/config/configStore";

const root = ReactDOM.createRoot(document.getElementById("root"));
root.render(
  <Provider store={store}>
    <React.StrictMode>
      <RouterConfig />
    </React.StrictMode>
  </Provider>
);

reportWebVitals();
```

```
// configStore.js
import { configureStore } from "@reduxjs/toolkit";
import data from "../modules/dataSlice";

const store = configureStore({
  reducer: {
    data: data,
  },
});

export default store;
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/b890fe27-e764-4c61-a5e5-a56cc4cd11f3)

