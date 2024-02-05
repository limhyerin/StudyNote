## 🙉 Step1 로그인 페이지 구현해보기 🙉

우선 기능없이 해당 페이지만 똑같이 구현을 해보았다. ID값과 PW값을 입력할 수 있는 칸을 위해 <input>태그와 <button> 태그를 이용하여 구현을 하였고 로그인 버튼도 작성하였다.
![image](https://github.com/limhyerin/StudyNote/assets/70150896/c723d378-d32c-47fb-9598-9c3d153a6615)

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <h1>로그인 페이지</h1>
    <p>ID: <input type="text"/></p>
    <p>PW: <input type="text"/></p>
    <button>로그인하기</button>
</body>
</html>
```

 

## 🙉 Step2 CSS 연습하기 🙉
![image](https://github.com/limhyerin/StudyNote/assets/70150896/48c194c6-0eb0-49c0-bc7d-ada4daa897dc)

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .mytitle {
            width: 300px;
            height: 200px;
            color: white;
            text-align: center;
            
            padding-top: 40px;
            border-radius: 8px;

            background-image: url('https://www.ancient-origins.net/sites/default/files/field/image/Agesilaus-II-cover.jpg');
            background-position: center;
            background-size: cover;
        }
    </style>
</head>
<body>
    <div class="mytitle">
        <h1>로그인 페이지</h1>
        <h5>아이디, 비밀번호를 입력해주세요</h5>
    </div>
    <p>ID: <input type="text"/></p>
    <p>PW: <input type="text"/></p>
    <button>로그인하기</button>
</body>
</html>
``` 
