# 🎃 reduce 🎃
reduce의 acc는 배열의 첫번째 인덱스에 있는 값이 들어가고 그 뒤로는 undefined 값이 들어가게 된다. 그리고 cur에는 배열의 첫번째 요소를 제외한 나머지가 들어가게 된다
![image](https://github.com/limhyerin/TIL/assets/70150896/cba137d1-fa50-4b0c-a681-0623bffbd9b1)

```js
const handleReduce = () => {
    const reducedListText = array.reduce(function (acc, cur) {
      return `${acc}, ${cur}`;
    });
    setResult(reducedListText);
  };
```
