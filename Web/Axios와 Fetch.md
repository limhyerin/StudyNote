fetch와 axios
axios를 쓰는 이유? api를 가져올 때

```
yarn add axios
```

```
yarn add json-server
```

```
yarn json-server --watch db.json --port 4000
```

```
import { useEffect } from 'react';
import axios from "axios";
import './App.css';

function App() {

  const fetchTodos = async () => {
    // const response = await axios.get("http://localhost:3001/todos");
    // console.log('response', response);
    const { data } = await axios.get("http://localhost:3001/todos");
    console.log('data', data);
  }
  useEffect(() => {
    // db로부터 값을 가져올 것이다.
    fetchTodos();
  }, [])
  return (
    <div>
      AXIOS
    </div>
  );
}

export default App;
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/8e898c32-75f1-4d5c-b3ed-47b10380bd62)

```
import { useEffect } from 'react';
import axios from "axios";
import './App.css';

function App() {

  const fetchTodos = async () => {
    // const response = await axios.get("http://localhost:3001/todos");
    // console.log('response', response);
    const { data } = await axios.get("http://localhost:3001/todos");
    console.log('data', data);
  }
  useEffect(() => {
    // db로부터 값을 가져올 것이다.
    fetchTodos();
  }, [])
  return (
    <div>
      AXIOS
    </div>
  );
}

export default App;

```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/56cbd7f5-dddc-4d0a-8338-c6195f67615c)


![image](https://github.com/limhyerin/StudyNote/assets/70150896/5e1aa10c-c341-4f55-ba66-5e52fcb44eb0)

![image](https://github.com/limhyerin/StudyNote/assets/70150896/c2c811c7-8613-424e-bf2f-ad884aa1b82d)

TypeError: Cannot read property 'map' of null
```
return (
    <div>
      {todos?.map((item) => {
        return (
        <div key={item.id}>
          {item.id} : {item.title}
        </div>
        );
      })}
    </div>
  );
```
