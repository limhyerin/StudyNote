# 🎃 push 🎃
입력한 값이 없는 상태로 push 버튼을 클릭한다면 값이 없다는 alert창을 띄우고 false를 반환한다. 그리고 값을 입력했다면 newArr 배열을 새롭게 만들어서 기존의 array 배열을 풀어서 뒤에 입력값을 넣어준다. 그리고 array의 값을 추가된 값으로 변경시켜준다.
![image](https://github.com/limhyerin/TIL/assets/70150896/c4cd662f-eff5-4cc6-900e-7db5e5057f45)

```js
const handlePush = () => {
    if (!query) {
      alert("값이 없습니다!");
      return false;
    }
    const newArr = [...array, query];
    setArray(newArr); // 추가된 값을 원본 값에 저장하는것
    setResult(newArr.join(", ")); // 배열 뒤에 값을 붙이는 것
  };
```
