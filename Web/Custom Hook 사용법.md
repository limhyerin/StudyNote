# 🌻Custom Hook🌻
우리는 react에서 제공하는 useState와 같은 hook을 사용한다. 그런데 우리가 원하는대로 hook을 만들어서 사용할 수도 있다.

![image](https://github.com/limhyerin/StudyNote/assets/70150896/1e632c70-0ab2-4416-b84f-f9650f7f3163)

<br/>

## 🌼기존 useState 사용 코드🌼
### App.jsx
```js
import { useState } from 'react';
import './App.css';

function App() {
  const [name,setName] = useState('');
  const [password, setPassword] = useState('');

  const onChangeNameHandler = (e) => {
    setName(e.target.value);
  }

  const onChangePasswordHandler = (e) => {
    setPassword(e.target.value);
  }

  return (
    <div>
      <input type='text' value={name} onChange={onChangeNameHandler}/>
      <input type='text' value={password} opnChange={onChangePasswordHandler}/>
    </div>
  );
}

export default App;
```

<br/>

## 🌼useInput hook을 만들고 적용🌼
### useInput.js
```js
import { useState } from "react";

const useInput = () => {
    // state
    const [value, setValue] = useState('');

    // handler
    const handler = (e) => {
        setValue(e.target.value);
    };

    return [value, handler];
}

export default useInput;
```

### App.jsx
```js
import useInput from './hooks/useInput';
import './App.css';

function App() {
  const [name,onChangeNameHandler] = useInput('');
  const [password, onChangePasswordHandler] = useInput('');

  return (
    <div>
      <input type='text' value={name} onChange={onChangeNameHandler}/>
      <input type='text' value={password} opnChange={onChangePasswordHandler}/>
    </div>
  );
}

export default App;
```
