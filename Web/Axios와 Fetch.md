# 🎃fetch와 axios🎃
axios를 쓰는 이유? api를 가져올 때

<br/>

## 🌻axios 설치🌻
```
yarn add axios
```

## 🌻json-server 설치🌻
```
yarn add json-server
```

## 🌻포트 설정🌻
```
yarn json-server --watch db.json --port 4000
```

<br/>

## 🌼db.json🌼
```
// db.json
{
  "users": [
    {
      "id": 1,
      "name": "John Doe",
      "email": "johndoe@example.com"
    },
    {
      "id": 2,
      "name": "Jane Doe",
      "email": "janedoe@example.com"
    }
  ],
  "posts": [
    {
      "id": 1,
      "userId": 1,
      "title": "John's first post",
      "body": "This is the content of John's first post."
    },
    {
      "id": 2,
      "userId": 1,
      "title": "John's second post",
      "body": "This is the content of John's second post."
    },
    {
      "id": 3,
      "userId": 2,
      "title": "Jane's first post",
      "body": "This is the content of Jane's first post."
    }
  ]
}

```

<br/>

## 🌼api.js🌼
```
import axios from 'axios';

const api = axios.create({
  baseURL: 'http://localhost:3000', // json-server의 주소를 기본 URL로 설정
});

api.interceptors.request.use((config) => {
  console.log('요청합니다.');
  return config;
});

api.interceptors.response.use((response) => {
  console.log('응답입니다.');
  return response;
}, (error) => {
  return Promise.reject(error);
});

export default api;
```

<br/>

## 🌼App.jsx🌼
```
import React, { useEffect, useState } from 'react';
import api from './api';

function App() {
  const [posts, setPosts] = useState([]);

  useEffect(() => {
    const fetchPosts = async () => {
      try {
        const response = await api.get('/posts');
        setPosts(response.data);
      } catch (error) {
        console.error('There was an error!', error);
      }
    };

    fetchPosts();
  }, []);

  return (
    <div>
      <h1>Posts</h1>
      {posts.map(post => (
        <div key={post.id}>
          <h2>{post.title}</h2>
          <p>{post.body}</p>
        </div>
      ))}
    </div>
  );
}

export default App;
```
