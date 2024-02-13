# 🎃 filter 🎃
검색한 단어가 있는지 필터링을 하고 꼭 모든 글자를 다 입력하지 않더라도 includes를 통해 입력한 값에 해당하는 문자혹은 문자열이 배열안에 있다면 Result에 반환하도록 한다.
![image](https://github.com/limhyerin/TIL/assets/70150896/7208dc42-905c-4709-8f91-c242775b48f5)

```js
const handleFilter = () => {
    const filteredList = array.filter(function (fruit) {
      // 얘를 필터링을 할지 말지를 결정한다.
      if (fruit.includes(query)) {
        return true;
      } else {
        return false; // 여기서 결정한다.
      }
    });
    setResult(filteredList.join(", "));
  };
 ```
