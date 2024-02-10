Error fetching nickname: FirebaseError: Missing or insufficient permissions.

step1 firebase 사이트에서 규칙 클릭
![image](https://github.com/limhyerin/StudyNote/assets/70150896/6f18f879-d8d9-48a0-92f2-2cf23bccd5a1)

아래 처럼 작성되어 있는 부분을
```
rules_version = '2';

service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if false;
    }
  }
}
```

이렇게 바꾸어준다
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```
