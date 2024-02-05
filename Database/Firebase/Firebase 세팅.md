# 🎃 Firebase 세팅 🎃
먼저 script에 type 추가하고
```html
<script type="module">
```
그다음 파이어 베이스 세팅 코드를 script안에 추가하고 firebase 구성정보 설정 부분을 모두 지워서 자신의 설정 내용으로 채운다.
```js
// Firebase 세팅
// Firebase SDK 라이브러리 가져오기
import { initializeApp } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-app.js";
import { getFirestore } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-firestore.js";
import {
        collection,
        addDoc,
} from "https://www.gstatic.com/firebasejs/9.22.0/firebase-firestore.js";
import { getDocs } from "https://www.gstatic.com/firebasejs/9.22.0/firebase-firestore.js";

// Firebase 구성 정보 설정
// For Firebase JS SDK v7.20.0 and later, measurementId is optional
const firebaseConfig = {
        apiKey: "AIzaSyAFae2toPUP6oww6ri_etBpuYUtd07MDlk",
        authDomain: "sparta-52b8f.firebaseapp.com",
        projectId: "sparta-52b8f",
        storageBucket: "sparta-52b8f.appspot.com",
        messagingSenderId: "68006099126",
        appId: "1:68006099126:web:9e958e631d289e6c7b8e17",
        measurementId: "G-8GV5KMXCPV",
};

// Firebase 인스턴스 초기화
const app = initializeApp(firebaseConfig);
const db = getFirestore(app);
```

프로젝트 설정 - SDK설정 및 구성 - 구성 코드 복사해서 위의 코드의 '본인 설정 내용 채우기' 부분에 채워넣는다. <br/>

![image](https://github.com/limhyerin/TIL/assets/70150896/53780261-0be8-4bd1-a27e-b6c0b70520f1)
![image](https://github.com/limhyerin/TIL/assets/70150896/f6e2f1d6-db12-4038-b39c-03099deec84b)
