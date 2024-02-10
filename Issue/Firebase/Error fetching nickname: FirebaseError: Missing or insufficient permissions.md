# 🚨error code🚨
firebase에서 nickname값을 가져오는 부분에서 발생한 오류
```
Error fetching nickname: FirebaseError: Missing or insufficient permissions.
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/6f18f879-d8d9-48a0-92f2-2cf23bccd5a1)

<br/>

## 1. 기존 코드
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

<br/>

## 2. 변경 코드
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
