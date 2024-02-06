# 🌕 content 🌕
>01 indexOf() - 인덱스 반환 <br/>
02 lastIndexOf() - 동일한 결과, 가장 마지막 인덱스 반환 <br/>
03 includes() - 특정요소를 포함하고 있는지 판별, 참-거짓 <br/>
04 find() - 조건에 해당하는 첫번째 값 하나만 리턴 <br/>
05 filter() - 조건에 해당하는 모든 값을 배열로 리턴 <br/>
06 some() <br/>
07 search() - 문자열이 시작하는 인덱스 리턴 <br/>

 <br/>
 
## 01 indexOf() - 인덱스 반환
배열 요소의 위치를 찾고자 하는 경우에 사용 <br/>
있으면 해당 요소의 배열 인덱스를 반환하고 없으면 -1을 반환한다. 대소문자와 공백을 구분 <br/>
```js
const arr = ['one', 'two', 'three'];
console.log(arr.indexOf('one')); // 0
```
Array.indexOf()에 2번째 인자로 시작할 인덱스 번호를 넣을 수 있다.
 <br/>
첫 번째 인자는 배열에서 찾을 요소를 넣었다면, 두번째 인자는 선택사항으로 해당 배열에서 시작하고자 하는 위치를 넣어 검색할 수 있다. 기본값은 0이며 배열의 크기보다 인덱스를 크게 잡는 경우 -1이 리턴된다.
```js
const arr = ['one', 'two', 'three'];
console.log(arr.indexOf('one', 2)); // -1
```

 <br/> 

## 02 lastIndexOf() - 동일한 결과, 가장 마지막 인덱스 반환
배열에서 주어진 값 중 동일한 결과가 있다면 가장 마지막에 있는 결과값을 반환 <br/>
요소가 존재하지 않으면 -1을 반환하는 등 indexOf()와 특징은 동일 <br/>
```js
const arr = ['one', 'two', 'three', 'two'];
console.log(arr.indexOf('one')); // 0
console.log(arr.lastIndexOf('two')); // 3
``` 

Array.lastIndexOf()에 두번째 인자로 역순으로 검색을 시작할 인덱스를 넣을 수 있다.
 <br/>
기본값은 array.length-1이다.
음수를 넣더라도 검색 순서는 뒤에서 앞으로 시작된다.
두번째 인자 값이 음수라면 배열의 마지막부터 시작하는 인덱스로 처리된다.

 <br/> 

## 03 includes() - 특정요소를 포함하고 있는지 판별, 참-거짓
특정 요소를 포함하고 있는지 판별, true 또는 false를 반환 <br/>

문자나 문자열 비교시 대소문자를 구분하며 엄격한 비교 ===를 사용하므로 비교 연산자가 사용된다면 사용에 주의가 필요하다. <br/>
객체와 객체를 비교하는 경우엔 include()가 아닌 다른 메서드를 사용하는 것이 좋다. <br/>
```js
const arr = [["빨강", "red"],["파랑", "blue"]];

arr.forEach((elem) => {
  if(elem.includes('red')){
    console.log(elem); // (2) ["빨강", "red"]
    console.log(elem.includes('red')); // true
  }
});
```

includes()의 두번째 인자로 검색을 시작할 인덱스를 넣을 수 있다. <br/>

console.log(["하나", "둘", "셋"].includes('하나', 1)); //false <br/>
배열의 길이보다 크거나 같으면 false가 반환된다. <br/>

 <br/> 

## 04 find() - 조건에 해당하는 첫번째 값 하나만 리턴
첫번째 인자로 콜백함수를 넣어 함수를 만족하는 첫번째 값을 반환하는 메서드이다. <br/>
만족하지 않으면 undefined를 반환한다. <br/>
```js
const arr = [
  {
    name : '아이유',
    age : 30
  },
  {
    name : '은하',
    age : 26
  }
]

const result = arr.find((elem)=>{
  return elem.name === '아이유';
})

console.log(result); // {name: "아이유", age: 30}
```
find()의 첫번째 인자 콜백함수는 최대 3개의 인자를 가질 수 있다.
```js
arr.find((elem, idx, arr) => {
  console.log(elem, idx, arr); //처리할 요소/인덱스/find를 호출한 배열
})
``` 

find()의 두번째 인자는 this로 사용할 객체가 들어간다. <br/>
콜백이 호출될 때 this로 사용할 객체를 선택사항(옵션)으로 넣어줄 수 있다. <br/>
인덱스를 반환해주는 findIndex()라는 메서드도 존재한다. <br/>

 <br/>
 
## 05 filter() - 조건에 해당하는 모든 값을 배열로 리턴
![image](https://github.com/limhyerin/StudyNote/assets/70150896/d5dfc8aa-e6fb-404a-a868-c9260ab81041)

find()는 조건에 해당하는 첫번째 값 하나만 리턴하는 반면 <br/>
filter()는 조건에 해당하는 모든 값을 배열로 리턴하는 메서드이다. <br/>
파라미터와 사용방법은 find()함수와 동일하다. <br/>
```js
const music = [
  {
    artist: "아이유",
    song: "좋은날"
  },
  {
    artist: "아이유",
    song: "블루밍"
  },
  {
    artist: "VIVIZ",
    song: "BOP BOP!"
  }
];

const result = music.filter((elem) => {
  return (elem.artist === "아이유");
});

console.log(result);
```

찾고자 하는 요소에 해당하는 모든 것을 배열로 반환해주었다.

 <br/> 

## 06 some()
빈 배열에서 호출하면 false가 반환된다. <br/>
배열 안의 모든 요소중 최소 1개 이상이 주어진 콜백함수를 통과하면 true를 반환한다. <br/>
첫번째 인자로는 콜백함수를 받는다. 콜백함수는 최대 3개의 인자를 사용할 수 있다. <br/>
some(콜백함수(처리할 요소, 인덱스, 호출한 배열), thisArg{}) <br/>
두번째 인자는 선택사항으로 콜백함수 실행시 this로 사용될 값을 넣어줄 수 있다. <br/>
```js
const arr = ["아이유", "이지은", "이지금"];

console.log(
  arr.some((elem)=>{
    return elem === "이지금"
  })
); // true
``` 

 <br/> 

## 07 search() - 문자열이 시작하는 인덱스 리턴
```js
const str = 'HTML,CSS,JavaScript';
const pos1 = str.search('JavaScript');
// 결과 : 9

const pos2 = str.search('Kotlin');
// 결과 : -1
``` 

>search("찾을 문자열") <br/>
: search 함수는 정규식을 사용하여 문자열을 찾을 수 있습니다. search 함수는 indexOf 함수와 동일하게 문자열을 찾을 수 있습니다. 다만 search 함수는 문자열을 찾을 때 시작 위치는 지정할 수는 없습니다. 
```js
/* 한글 찾기 */
const str = 'HTML,CSS,자바스크립트';
const pos = str.search(/[ㄱ-ㅎ|ㅏ-ㅣ|가-힣]/);
// 결과 : 9
/* 대소문자 구분없이 검색 */
const str = 'HTML,CSS,JavaScript';
const pos = str.search(/javascript/gi);
// 결과 : 9
```
