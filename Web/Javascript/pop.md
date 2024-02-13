# 🎃 pop 🎃
pop함수는 뒤에 있는 값들을 제거해주는 함수로 Array 배열에 담겨있는 요소들을 맨뒤에 인덱스의 값부터 삭제 시켜주게 된다.
![image](https://github.com/limhyerin/TIL/assets/70150896/cc3eefda-c682-4ad6-ac04-f351f95fe742)

```js
const handlePop = () => {
    const newArr = [...array];
    newArr.pop();
    setArray(newArr);
    setResult(newArr.join(", "));
  };
 ```

각각 button을 클릭했을때 해당 함수로 정의해둔 기능들이 구현될 수 있도록 한다.
```html
<button onClick={handleForEach}>forEach</button>
<button onClick={handleFilter}>filter</button>
<button onClick={handleMap}>map</button>
<button onClick={handleReduce}>Reduce</button>
<button onClick={handlePush}>Push</button>
<button onClick={handlePop}>Pop</button>
``` 
