# 🌻라우터(Router) 설정🌻
<br/>

## App.jsx
```js
import './App.css';
import { BrowserRouter, Routes, Route } from "react-router-dom";
import Home from './pages/Home';
import Company from './pages/Company';

function App() {
  return (
    <BrowserRouter>
      <Routes>
        <Route path="/" element={<Home />}/>
        <Route path="/company" element={<Company />}/>
      </Routes>
    </BrowserRouter>
  );
}

export default App;
```

<br/>

## Home.jsx
![image](https://github.com/limhyerin/StudyNote/assets/70150896/52d2863d-75bc-4a3e-b2ae-c8614d310526)
```
import React from "react";

function Home() {
    return (
     <div style={{
        paddingLeft: 20,
        paddingRight: 20,
     }}><h1>Button 이벤트 예제</h1>
     </div>   
    )
}

export default Home;
```

<br/>

## Company.jsx
![image](https://github.com/limhyerin/StudyNote/assets/70150896/0ccb0008-22c2-42c2-8c29-15a5665d8b7c)

```
import React from 'react'

const Company = () => {
  return (
    <div>Company</div>
  )
}

export default Company
```
