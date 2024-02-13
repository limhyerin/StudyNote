# 🎃 map 🎃
map함수를 통해 배열의 값들을 원하는 값으로 바꿔서 다시 출력하도록 할 것인데 그 중에서도 각 배열의 요소들을 대문자로 변경하여 출력하도록 한다. toUpperCase를 통해 각 요소들을 하나하나 대문자로 바꿔주고 배열을 하나의 문자열로 join하여 출력한다
![image](https://github.com/limhyerin/TIL/assets/70150896/1946188e-9bf3-4aff-83e7-dc891b96f08f)

```js
const handleMap = () => {
    // array를 대문자로 변환하여 출력
    const mappedList = array.map(function (fruit) {
      return fruit.toUpperCase();
    });
    setResult(mappedList.join(", "));
  };
```
