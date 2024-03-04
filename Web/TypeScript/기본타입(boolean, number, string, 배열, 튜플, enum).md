# 🌳기본타입🌳
## 01 boolean이란?
- 2가지의 상태(켜짐/꺼짐, 유효함/유효하지 않음)를 표현하고 싶은 경우 → boolean을 사용
- 3가지 이상의 상태를 표현하고 싶은 경우 → enum이나 string을 사용
- boolean 타입은 참(true) 또는 거짓(false) 값을 나타냄
- 조건문, 비교 연산 등에서 주로 사용

#### 사용 사례
```ts
function isValidPassword(password: string): boolean {
  return password.length >= 8;
}
const password = "q1w2e3r4!";
const valid = isValidPassword(password);
if (valid) {
  console.log("유효한 패스워드입니다!");
} else {
  console.log("유효하지 않은 패스워드입니다!");
}
```

<br/>

## 02 number란?
number 타입은 TypeScript에서 사용하는 모든 숫자를 나타냄
- 정수 : short, int, long
- 실수 : float, double

하지만, TypeScript에서는 number 타입이 정수, 실수 뿐 아니라 2, 8, 16진수까지 표현 가능
모든 수치 연산에 사용되는 값은 number 타입으로 명시!

#### ☑️ 사용 사례
```ts
function calculateArea(radius: number): number {
  return Math.PI * radius * radius;
}

const radius = 5;
const area = calculateArea(radius);
console.log(`반지름이 ${radius}인 원의 넓이: ${area}`);
```

<br/>

## 03 string이란?
- 작은 따옴표(’), 큰 따옴표(”), 백쿼트(`) 를 사용하여 문자열을 표현할 수 있음

#### ☑️ 사용 사례
```
function greet(name: string): string {
  return `안녕, ${name}!`;
}

const name = "Spartan";
const greeting = greet(name);
console.log(greeting);
return 안녕, ${name}!; 이 템플릿 리터럴
```

<br/>

## 배열이란?
배열은 기본타입에 []가 붙은 형태의 타입

#### ☑️ 사용 사례
```ts
function calculateSum(numbers: number[]): number {
  let sum: number = 0;
  for (let i = 0; i < numbers.length; i++) {
    sum += numbers[i];
  }
  return sum;
}

const testScores: number[] = [90, 85, 78, 92, 88];
const sumScore = calculateSum(testScores);
console.log(`점수의 총합: ${sumScore}`);
```

<br/>

## 튜플이란?
튜플은 서로 다른 타입의 원소를 순서에 맞게 가질 수 있는 특수한 형태의 배열

### 튜플과 배열의 차이
배열 : number[], string[] 처럼 같은 타입의 원소만 가질 수 있음. <br/>
ex) const testScores: number[] = [90, 85, 78, 92, “88”]; // Error

<br/>

튜플 : 어떤 타입의 원소를 허용할 것인지 정의만 해주면 됌. 얼마든지 허용된 타입의 데이터들을 저장할 수 있음

#### ☑️ 사용 사례
```ts
const person: [string, number, boolean] = ['Spartan', 25, false];
const person2: [string, number, boolean] = [25, 'Spartan', false]; // 오류!
```
여기서는 string, number, boolean이라는 3개의 각각 다른 타입의 데이터를 보관하게 정의를 했어요!

<br/>

☑️ enum이란?
- enum은 열거형 데이터 타입
- 다양한 상수를 보다 더 이해하기 쉬운 문자열 이름으로 접근하고 사용할 수 있게 하는 타입입니다!
- enum 안에 있는 요소에는 number 혹은 string타입의 값만을 할당할 수 있어요!
```ts
enum UserRole {
  ADMIN = "ADMIN",
  EDITOR = "EDITOR",
  USER = "USER",
}

enum UserLevel {
  NOT_OPERATOR, // 0
  OPERATOR // 1
}

function checkPermission(userRole: UserRole, userLevel: UserLevel): void {
  if (userLevel === UserLevel.NOT_OPERATOR) {
    console.log('당신은 일반 사용자 레벨이에요');
  } else {
    console.log('당신은 운영자 레벨이군요');
  } 

  if (userRole === UserRole.ADMIN) {
    console.log("당신은 어드민이군요");
  } else if (userRole === UserRole.EDITOR) {
    console.log("당신은 에디터에요");
  } else {
    console.log("당신은 사용자군요");
  }
}

const userRole: UserRole = UserRole.EDITOR;
const userLevel: UserLevel = UserLevel.NOT_OPERATOR;
checkPermission(userRole, userLevel);
```
