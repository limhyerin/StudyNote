# 🎃 foreach 🎃
foreach문을 통해 Array 배열에 있는 요소들을 하나하나 다 빼와서 붙여주고 마지막에 따라붙는 ,와 공백을 없애주기 위해 slice를 사용하여 첫번째 요소부터 -2인덱스전까지 출력하도록 해준다

![image](https://github.com/limhyerin/TIL/assets/70150896/b8bb5487-ef94-442c-b021-67f2937ee1c9)


```js
const handleForEach = () => {
    let tempResult = "";
    array.forEach(function (fruit) {
      tempResult += `${fruit} ,`;
    });
    // tempResult = tempResult.slice(0, -2);
    // setResult(tempResult);
    setResult(tempResult.slice(0, -2));
  };
```
