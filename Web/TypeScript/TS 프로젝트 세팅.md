# 프로젝트 세팅
--rootDir ./src <br/>
프로그램의 소스 파일이 들어가는 경로는 src 디렉토리입니다. <br/>
--outDir ./dist <br/>
컴파일이 된 파일들이 들어가는 디렉토리는 dist 디렉토리입니다. <br/>
--esModuleInterop <br/>
CommonJS 방식의 모듈을 ES모듈 방식의 import 구문으로 가져올 수 있습니다! <br/>

<br/>

## 01 명령어 입력
```bash
npm init -y
```
```bash
tsc --init --rootDir ./src --outDir ./dist --esModuleInterop --module commonjs --strict true --allowJS true --checkJS true
```

<br/>

## 02 package.json의 “scripts” 항목을 다음과 같이 변경
```json
"scripts": {
    "start": "tsc && node ./dist/index.js",
    "build": "tsc --build",
    "clean": "tsc --build --clean"
},
```
![image](https://github.com/limhyerin/StudyNote/assets/70150896/090ada7d-07b7-48ef-83a9-e9cf171e31c9)

<br/>

## 03 src 디렉토리 생성
![image](https://github.com/limhyerin/StudyNote/assets/70150896/2d4d41b0-06a7-4843-9c8d-456e12b02afd)


░▒▓ ~/w/first_typescript ▓▒░ ls -al                     ░▒▓ ✔ │ 08:01:29 PM ▓▒░ <br/>
total 32 <br/>
drwxr-xr-x   5 chris  staff    160  5  4 20:11 . <br/>
drwxr-xr-x  32 chris  staff   1024  5  4 18:35 .. <br/>
-rw-r--r--   1 chris  staff    230  5  4 19:08 package.json <br/>
drwxr-xr-x   3 chris  staff     96  5  4 20:11 src <br/>
-rw-r--r--   1 chris  staff  11298  5  4 20:10 tsconfig.json <br/>
