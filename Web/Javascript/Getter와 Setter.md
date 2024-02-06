# 🎃 Getter, Setter 🎃
class에서는 getter와 setter를 사용하여 class의 속성에 접근할 수 있다. <br/>

- getter : 속성 값을 반환하는 메소드
- setter : 속성 값을 설정하는 메소드
 

 <br/>
 
## 🎃 가로 세로 값을 입력받아서 넓이를 출력하는 프로그램 🎃
setter를 통해 외부로부터 받아온 value를 내부적으로 점검한 후에 검증 및 세팅을 한다.  <br/>

undersocore : 변수이름 앞에 언더바를 붙여서 외부에서 접근할 수 없는 숨겨진 필드임을 나타내는 방식 <br/>

(인스턴스 내에서만 사용하기 위해)
```js
class Rectangle {
    constructor(height, width) {
        this._height = height;
        this._width = width;
    }

    get width() {
        return this._width;
    }

    set width(value) {
        if(value <= 0) {
            console.log("[오류] 가로길이는 0보다 커야합니다");
            return; // 함수 빠져나옴
        } else if(typeof value != 'number') {
            console.log("[오류] 가로길이로 입력된 값이 숫자타입이 아닙니다");
            return; // 함수 빠져나옴
        }
        this.width = value;
    }

    get height() {
        return this._height;
    }

    set height(value) {
        if(value <= 0) {
            console.log("[오류] 가로길이는 0보다 커야합니다");
            return; // 함수 빠져나옴
        } else if(typeof value != 'number') {
            console.log("[오류] 가로길이로 입력된 값이 숫자타입이 아닙니다");
            return; // 함수 빠져나옴
        }
        this.height = value;
    }

    getArea() {
        // 가로 * 세로 ==> 넓이
        const a = this._height * this._width;
        console.log(`넓이는 ${a}입니다.`);
    }
}

const rect1 = new Rectangle(10, 7);
const rect2 = new Rectangle(10, 30);
const rect3 = new Rectangle(15, 20);
rect1.getArea();
rect2.getArea();
rect3.getArea();
```
underscore(_)를 사용하지 않았다면 setters, getters 둘 다에서 무한루프에 빠지게 되는 경우가 있을 수 있다.

 <br/>
 
## 🎃 배운 내용을 토대로 Car 클래스에 적용해보기 🎃
### 요구사항
#### 1. Car라는 새로운 클래스를 만들되, 처음 객체를 만들 때는 // 다음 네 개의 값이 필수로 입력돼야 합니다!
(1) modelName
(2) modelYear
(3) type : 가솔린, 전기차, 디젤
(4) price

 <br/>
 
#### 2. makeNoise() 메서드를 만들어 클락션을 출력해주세요
2-1. 해당 자동차가 몇년도 모델인지 출력하는 메서드 작성!

 <br/>
 
#### 3. 이후 자동차를 3개 정도 만들어주세요(객체 생성)
### 추가 요구사항
#### 1. modelName, modelYear, price, type을 가져오는 메서드
#### 2. modelName, modelYear, price, type을 세팅하는 메서드
#### 3. 만든 인스턴스를 통해서 마지막에 set 해서 get 하는 로직까지
```js
class Car {
    constructor(modelName, modelYear, type, price) {
      this._modelName = modelName;
      this._modelYear = modelYear;
      this._type = type;
      this._price = price;
    }
  
    get modelName() {
      return this._modelName;
    }
  
    // 입력값에 대한 검증까지 가능하다
    set modelName(value) {
      // 유효성 검사
      if (value.length <= 0) {
        console.log("[오류] 모델명이 입력되지 않았습니다. 확인해주세요!");
        return;
      } else if (typeof value !== "string") {
        console.log("[오류] 입력된 모델명이 문자형이 아닙니다!");
        return;
      }
  
      // 검증이 완료된 경우에만 setting!
      this._modelName = value;
    }
  
    get modelYear() {
      return this._modelYear;
    }
  
    set modelYear(value) {
      // 유효성 검사
      if (value.length !== 4) {
        // 연도에 대한 유효성 검증 로직 ---> googling 엄청~~~~많이 나옵니다!!
        console.log("[오류] 입력된 년도가 4자리가 아닙니다.확인해주세요!");
        return;
      } else if (typeof value !== "string") {
        console.log("[오류] 입력된 모델명이 문자형이 아닙니다!");
        return;
      }
  
      // 검증이 완료된 경우에만 setting!
      this._modelYear = value;
    }
  
    get type() {
      return this._type;
    }
  
    set type(value) {
      if (value.length <= 0) {
        console.log("[오류] 타입이 입력되지 않았습니다. 확인해주세요!");
        return;
      } else if (value !== "g" && value !== "d" && value !== "e") {
        // g(가솔린), d(디젤), e(전기차)가 아닌 경우 오류
        console.log("[오류] 입력된 타입이 잘못되었습니다. 확인해주세요!");
        return;
      }
  
      // 검증 완료!
      this._type = value;
    }
  
    get price() {
      return this._price;
    }
  
    set price(value) {
      if (typeof value !== "number") {
        console.log("[오류] 가격으로 입력된 값이 숫자가 아닙니다. 확인해주세요!");
        return;
      } else if (value < "1000000") {
        console.log("[오류] 가격은 100만원보다 작을 수 없습니다. 확인해주세요!");
        return;
      }
  
      // 검증이 완료된 경우
      this._price = value;
    }
  
    // 클락션을 울리는 메서드
    makeNoise() {
      console.log(this._modelName + ": 빵!");
    }
  
    // 해당 자동차가 몇년도 모델인지 출력하는 메서드 작성!
    printModelYear() {
      console.log(
        this._modelName + "은 " + this._modelYear + "년도의 모델입니다."
      );
    }
  }
  
  // 자동차 만들기
  const car1 = new Car("Sorento", "2023", "e", 5000);
  const car2 = new Car("SM5", "1999", "g", 3000);
  const car3 = new Car("Palisade", "2010", "d", 4500);
  // car1.makeNoise();
  // car1.printModelYear();
  // car2.makeNoise();
  // car2.printModelYear();
  // car3.makeNoise();
  // car3.printModelYear();
  
  // getter 예시1
  console.log(car1.modelName);
  // setter 예시1
  car1.modelName = 1;
  console.log(car1.modelName);
``` 

 <br/>
 
>Sorento <br/>
[오류] 입력된 모델명이 문자형이 아닙니다! <br/>
Sorento
