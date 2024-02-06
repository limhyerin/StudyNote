# 🎃 toUpperCase( ), toLowerCase( ) 🎃
### 👉 toUpperCase( )
문자열을 대문자로 변환하며, 변환 후 두 개의 문자열이 같은지 비교하면 됌
```
let a = "hello world";
let b = "Hello World";

if (a.toUpperCase() === b.toUpperCase()){
    alert("두 값이 같습니다")
} else {
    alert("두 값이 다릅니다")
}
```

>// 두 값이 같습니다

<br/>

### 👉 toLowerCase( )
문자열을 소문자로 변환하며, 변환 후 두 개의 문자열이 같은지 비교하면 됌
```
let a = "hello world";
let b = "Hello World";

if (a.toLowerCase() === b.toLowerCase()){
    alert("두 값이 같습니다")
} else {
    alert("두 값이 다릅니다")
}
```

>// 두 값이 같습니다

<br/>

toLowercase( )는 일부 언어의 경우 소문자로 변환되지 않는 경우도 있기 때문에 toUpperCase( )이 선호
