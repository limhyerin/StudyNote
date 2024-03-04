# 🌳tsconfig.json🌳
tsconfig.json은 TypeScript 프로젝트의 설정파일 <br/>
주로 프로젝트의 컴파일 옵션 및 입력 파일들을 정의하는데 사용 <br/>


## JavaScript 라이브러리를 TypeScript 프로젝트에서 사용해보기!
### 명령어 입력
```bash
npm init -y
```

### tsconfig.json을 생성하여 TypeScript 프로젝트로 변환
터미널에서 실행!
```bash
tsc --init
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/45f87822-631b-43e0-9db1-f32ac90ca39e)

### tsconfig.json을 열어서 아래의 옵션을 주석 해제하여 true로 설정
![image](https://github.com/limhyerin/StudyNote/assets/70150896/086aa2e0-1103-4324-a96a-7fcecce520d5)
![image](https://github.com/limhyerin/StudyNote/assets/70150896/da36d709-f867-4f03-8826-15807086af61)

```json
"allowJs": true // TypeScript 프로젝트에 JavaScript 파일 허용 여부
"checkJs": true // JavaScript 파일 타입 체크 여부
```

### TypeScript에서 사용하고 싶은 커스텀 JavaScript 라이브러리(test.js)를 만듦
![image](https://github.com/limhyerin/StudyNote/assets/70150896/25821887-cee6-4352-a326-dd7cadebba47)

```ts
/**
 * @param {number} a
 * @param {number} b
 * @returns {number}
 */
export function add(a, b) { // export를 넣지 않으면 import 할 수 없는 것 아시죠?
  return a + b;
}
```
위의 주석문은 JSDoc이다. <br/>
JSDoc은 API의 시그니처 (인자, 리턴 타입)를 설명하는 HTML 문서 생성기. JSDoc으로 자바스크립트 소스코드에 타입 힌트를 제공할 수 있음 <br/>
이제, JSDoc으로 타입 힌트가 제공된 test.js의 .d.ts 파일을 만든다. 터미널에서 실행! <br/>
```bash
npx tsc test.js --declaration --allowJs --emitDeclarationOnly --outDir types
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/d05dde36-8a61-4a60-81e6-15993bd662f6)

types/test.d.ts 파일을 확인하면 다음과 같이 생성이 되어 있다
```
/**
 * @param {number} a
 * @param {number} b
 * @returns {number}
 */
export function add(a: number, b: number): number;
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/8ab3f833-be5b-4add-b276-c74373285feb)


types/test.d.ts 파일을 확인하면 다음과 같이 생성이 되어 있습니다!

![image](https://github.com/limhyerin/StudyNote/assets/70150896/c900dc15-ffa0-4ad4-9c3d-460a036e6399)
```ts
import { add } from "./test";
console.log(add(1, 2));
```


이제 foo.ts 파일을 실행시켜 보겠습니다! 다음의 명령어를 복사 + 붙여넣기를 해서 터미널에서 실행해주세요! 실행하면 3이라는 숫자가 뜨며 정상적으로 실행이 됨을 확인 할 수 있어요!
```bash
npx ts-node foo.ts
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/cc4f2037-ab1f-4073-bd8e-288ac52f5c5f)

