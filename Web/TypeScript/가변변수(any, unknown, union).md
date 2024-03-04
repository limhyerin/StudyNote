# any와 unknown, union에 대하여
어쩔 수 없이 가변적인 타입의 데이터를 저장하고 싶다면 any를 쓰기보다는 unknown을 사용 <br/>
가변적인 타입을 일일이 정의할 수 있다면 union 사용이 가장 낫다 <br/>

<br/>

## any
TypeScript에서 any 타입은 모든 타입의 슈퍼 타입. 이는 어떤 타입의 값이든 저장할 수 있다는 의미 <br/>
JavaScript의 object 타입과 같은 최상위 타입

#### ☑️ 사용 사례
let anything: any; anything = 5; // 최초에는 숫자를 넣었지만 anything = 'Hello'; // 문자열도 들어가고요 anything = { id: 1, name: 'John' }; // JSON도 들어가네요
TypeScript에서 any를 쓰는게 맞나요? 🤔🤔🤔
TypeScript를 사용하는 주된 이유 중 하나는 프로그램의 타입 안정성을 확보하기 위한 것이었어요!
그런데, any 타입은 그러한 우리의 믿음을 송두리째 저버릴 수 있는 아주 위험한 친구에요.
any 타입은 코드의 안정성과 유지 보수성을 저해할 수 있어요. 가급적 사용을 하지 마셔야 합니다!

<br/>

## unknown
#### ☑️ any의 대체제 unknown이란?
unknown 타입은 any 타입과 비슷한 역할을 하지만 더 안전한 방식으로 동작합니다.
unknown 타입의 변수에도 모든 타입의 값을 저장할 수 있어요.
하지만, 그 값을 다른 타입의 변수에 할당하려면 명시적으로 타입을 확인해야 합니다!

#### ☑️ 사용 사례
let unknownValue: unknown = '나는 문자열이지롱!';
console.log(unknownValue); // 나는 문자열이지롱!

let stringValue: string;
stringValue = unknownValue; // 에러 발생! unknownValue가 string임이 보장이 안되기 때문!
stringValue = unknownValue as string;
console.log(stringValue); // 나는 문자열이지롱!
stringValue = unknownValue as string; 코드를 **Type Assertion(타입 단언)**이라고 합니다.
unkwown 타입의 변수를 다른 곳에서 사용하려면 타입 단언을 통해 타입 보장을 하여 사용할 수 있어요!
let unknownValue: unknown = '나는 문자열이지롱!';
let stringValue: string;

if (typeof unknownValue === 'string') {
  stringValue = unknownValue;
  console.log('unknownValue는 문자열이네요~');
} else {
  console.log('unknownValue는 문자열이 아니었습니다~');
}
타입 단언만이 답은 아닙니다!
typeof 키워드를 이용하여 타입 체크를 미리한 후 unknown 타입의 변수를 string 타입의 변수에 할당할 수 있어요!

<br/>

## union
#### unknown의 한계
unknown 타입이 그나마 재할당을 할 때 타입 체크가 되어서 안전함을 보장해요.
하지만, unknown 타입도 결국 재할당이 일어나지 않으면 타입 안전성이 보장이 되지 않아요ㅠㅠ

#### union이란?
이럴 때를 위해 union 타입이라는 것이 사용됩니다.
union 은 여러 타입 중 하나를 가질 수 있는 변수를 선언할 때 사용됩니다!
union은 | 연산자를 사용하여 여러 타입을 결합하여 표현합니다.

#### ☑️ 사용 사례
type StringOrNumber = string | number; // 원한다면 | boolean 이런식으로 타입 추가가 가능해요! 
function processValue(value: StringOrNumber) { 
  if (typeof value === 'string') { // value는 여기서 string 타입으로 간주됩니다. 
    console.log('String value:', value); 
  } else if (typeof value === 'number') { // value는 여기서 number 타입으로 간주되구요! 
    console.log('Number value:', value); 
  }
} 
processValue('Hello'); 
processValue(42);
잊지 말아야 할 것
TypeScript를 쓰면서 여러 타입을 하나의 변수로 해결하겠다는 생각은 가급적 지양해주세요!
이런 사소한 습관들이 여러분들의 코드의 안정성을 높이고 유지 보수성을 개선할 수 있다는 것을 명심해주세요!
