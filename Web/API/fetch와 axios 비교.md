# 🌻fetch🌻
```
const url = "https://jsonplaceholder.typicode.com/todos";

fetch(url)
.then((response) => response.json())
.then(console.log);
```

# 🌻axios🌻
```
const url = "https://jsonplaceholder.typicode.com/todos";

axios.get(url).then((response) => console.log(response.data));
```
