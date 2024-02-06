 # 🎃 split() 함수 🎃
: 문자열을 일정한 구분자로 잘라서 배열로 저장하기 위해서는 split() 함수를 사용
```js
string.split(separator, limit)
``` 

<br/>

## 01 구분자를 비우는 경우 : string.split();
```js
const str = "apple banana orange";
const arr = str.split();

document.writeln(arr); // apple banana orange
document.writeln(arr.length); // 1
``` 

<br/>
 
## 02 구분자에 띄어쓰기를 넣는 경우 : string.split(" ");
공백을 기준으로 단어 하나하나씩을 배열에 순서대로 저장한다.
```js
const str = "apple banana orange";
const arr = str.split(" ");

document.writeln(arr.length); // 3
document.writeln(arr[0]); // apple
document.writeln(arr[1]); // banana
document.writeln(arr[2]); // orange
``` 

<br/> 

## 03 구분자에 따옴표만 넣는 경우 : string.split();
공백까지 배열에 포함되어 저장된다.
```js
const str = "a b c";
const arr = str.split("");

document.writeln(arr.length); // 5
document.writeln(arr[0]); // a
document.writeln(arr[1]); // ' '(space)
document.writeln(arr[2]); // b
document.writeln(arr[3]); // ' '(space)
document.writeln(arr[4]); // c
``` 

<br/> 

## 04 구분자에 쉼표를 넣는경우 : string.split(",");
쉼표를 기준으로 각각의 문자를 배열에 저장한다.
```js
const str = "apple,banana,orange";
const arr = str.split(",");

document.writeln(arr.length); // 3
document.writeln(arr[0]); // apple
document.writeln(arr[1]); // banana
document.writeln(arr[2]); // orange
``` 

<br/> 

## 05 구분자에 쉼표와 숫자를 넣는경우 : string.split(",", 2);
쉼표를 기준으로 숫자에 적은 2개만 배열에 저장이 된다.
```js
const str = "apple,banana,orange";
const arr = str.split(",", 2);

document.writeln(arr.length); // 2
document.writeln(arr[0]); // apple
document.writeln(arr[1]); // banana
document.writeln(arr[2]); // undefined
```
