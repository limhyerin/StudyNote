# 🌳변수, 상수 : let, const, readonly🌳
const와 readonly는 불변성을 보장

<br/>

## let이란?
let 키워드를 사용하여 선언하면 변수가 됌
변수는 값을 변경할 수 있음

<br/>

## const란?
const 키워드를 사용하여 선언하면 변수가 아닌 상수가 됌. 상수는 값을 변경할 수 없음

#### ☑️ 사용 사례
```
const num: number = 5;
console.log(num);  // 출력: 5

num = 10;  // 에러: 'num'은 const로 선언되었으므로 다시 할당될 수 없음
const nums: number[] = [];
console.log(nums);  // 출력: []
nums.push(1); 
nums.push(2); 
console.log(nums);  // 출력: [1, 2]

nums = [];  // 에러: 'nums'는 const로 선언되었으므로 다시 할당될 수 없음
```

<br/>

## readonly란?
앞의 두 키워드는 JavaScript에서 많이 사용되는 키워드 <br/>
하지만, readonly는 TypeScript에서 등장한 키워드 <br/>
readonly는 TypeScript에서 객체의 속성을 불변으로 만드는 데 사용되는 키워드 <br/>
즉, 클래스의 속성이나 인터페이스의 속성을 변경할 수 없게 만들 수 있음

#### ☑️ 사용 사례
```
class Person { 
  readonly name: string;
  readonly age: number;

  constructor(name: string, age: number) {
    this.name = name;
    this.age = age;
  }
}

const person = new Person('Spartan', 30);

console.log(person.name);  // 출력: 'Spartan'
console.log(person.age);   // 출력: 30

person.name = 'Jane';  // 에러: 'name'은 readonly 속성이므로 다시 할당할 수 없음
person.age = 25;       // 에러: 'age'은 readonly 속성이므로 다시 할당할 수 없음
```
