# 변수 

```js
Q) managed와 unmanaged를 잘못이해한 것인가?
A) 
```

```js
//variable hoisting
Q) 변수 선언문이 코드의 선수로 끌어올려진 것처럼 동작한다면 
   여러가지 변수가 선언되었으면 그 중에 우선순위는 뭐가 되는 거지? 당연히 첫번째?
A)
```

```js
//배열 비구조화 할당?
//배열이나 객체의 속성을 해체하여 그 값을 개별변수에 담을 수 있게 하는 표현식 
```

```js
Q) 타입헝가리언케이스, DOM노드, observable?
A) 타입 + pascalcase 
A) $elem > $ = DOM node를 소유하고 있다는 것을 알려준다. 
A) 반응형 programming
```



## #1.변수란 무엇인가? 왜 필요한가?

```js
#Q.변수란 무엇인가? 왜 필요한가?
#A.저장된 값을 읽어들여 재사용하기 위해 사용하는 것 
	 변경가능한 데이터가 담길 수 있는 공간
   그 공간의 이름이 변수 이름 , 즉 식별자.
```



#### 자바스크립트가 연산하는 방식 

> 고유한 개인의 명칭
> 숫자 '10', 숫자'20' = 각각의 literal 
> 기호 ' + ' = 연산자

> 표현식에서의 명칭
> 10, 20 = operand 피연산자 
> ' + ' = operator 연산자

코드를 평가(evaluation)하기 전 10, 20, + 의 의미를 알고 있어야 하고 10+20이라는 표현식의 의미도 해석(parsing)할 수 있어야 한다. 

<img src="/Users/jeonsejin/typoraimge/image2.jpg" alt="image2" style="zoom:50%;" /> 

 

 *간단지식 

> 컴퓨터는 cpu를 사용해 연산하고 메모리를 사용해 
> 데이터를 기억한다.

<img src="/Users/jeonsejin/typoraimge/변수1.jpg" alt="변수1" style="zoom:50%;" /> 



### 변수가 필요한 이유와 변수

<img src="/Users/jeonsejin/typoraimge/변수2.jpg" alt="변수2" style="zoom:50%;" /> 

```js
//메모리 : 데이터를 저장할 수 있는 메모리 셀의 집합체 
//메모리 셀 : 크기 1바이트(8비트) 단위
> 각 셀은 고유의 메모리 주소를 갖는다.
> 컴퓨터는 1바이트 단위로 데이터를 저장하거나 읽는다.
//메모리 주소 : 메모리 공간의 위치를 나타낸다. 
> 0부터 시작해서 메모리의 크기만큼 정수로 표현
```

### 변수

```js
// 값의 위치를 가리키는 상징적인 이름 
// 하나의 값을 저장하기 위해 확보한 메모리 공간자체 
// 메모리 공간을 식별하기 위해 붙인 이름 
```

> ```js
>// 변수는 하나의 값을 저장하기 위한 수단이다.
> var userId = 1;
>var userName = 'Lee';
> 
>// 여러 개 값 지정방법 : 
> //객체나 배열 같은 자료구조를 사용하면 여러 개의 값을 하나로 그룹화해서 하나의 값처럼 사용할 수 있다.
> var user = { id: 1, name: 'Lee' };
> 
> var users = [
> { id: 1, name: 'Lee' },
> { id: 2, name: 'Kim' }
> ];
> ```
> 



## #2 식별자

- 어떤 값을 구별해서 식별할 수 있는 고유한 이름 

- 변수이름 = 식별자

- 식별자는 값이 아니라 **"메모리 주소"**를 기억하고 있다.

  <img src="/Users/jeonsejin/Library/Application Support/typora-user-images/스크린샷 2020-11-16 오후 11.51.35.png" alt="스크린샷 2020-11-16 오후 11.51.35" style="zoom:50%;" /> 

```js
//주의사항
//변수 이름: 메모리 공간을 식별하기 위한 별명
//식별자 : 메모리 주소의 이름 > 선언으로 존재 알림.
```

```js
Q) 변수이름과 식별자는 같은 건가? 다른건가? 
A) 다르다 
```



### #3 변수 선언 

1. 선언단계 : 변수이름 등록하여 엔진에 변수의 존재를 알림.
2. 초기화 단계 : 값을 저장하기 위한 메모리공간을 확보하고 
   암묵적으로 undefined를 할당해 초기화 

<img src="/Users/jeonsejin/typoraimge/image3.jpg" alt="image3" style="zoom:50%;" /> 

- 변수를 생성하는 것 

  > 저장하기 위한 메모리공간을 확보(allocate)하여 변수이름과 
  > 확보된 메모리 공간의 주소를 연결 (name binding)해서 
  > 값을 저장할 수 있게 준비하는 것 

- 선언 = **keyword** 사용 (var / let / const )

  > keyword? 
  > 자바스크립트 코드를 해석하고 실행하는 자바스크립트 엔진이 수행할 동작을 규정한 일종의 명령어 
  > 자바스크립트 엔진은 키워드를 만나면 자신이 수행해야 할 약속된 동작을 수행한다.

  

#### (1) var

- 선언단계와 초기화 단계 동시진행 

  > 초기화 단계(initialization)?
  > 변수가 선언된 이후로 최초로 값을 할당하는 것 

```js
var score; // 변수 선언(변수 선언문)
//변수 선언 후 변수에 값을 할당하지 않은 상태 
//확보된 메모리공간 = undefined으로 할당되어 초기화 

//undefined : 원시타입의 값 (primitive value)
```

![스크린샷 2020-11-16 오후 11.58.59](/Users/jeonsejin/Library/Application Support/typora-user-images/스크린샷 2020-11-16 오후 11.58.59.png) 

```js
//garbage value?
// 초기화 단계를 거치지 않고 확보된 메모리공간에 이전에 다른 
// 애플리케이션이 사용했던 값 
```

```js
//ReferenceError?(참조에러)
//선언하지 않은 채 식별자에 접근할 때 생기는 에러 
```



### #4 변수 선언의 실행 시점과 변수 호이스팅

```js
console.log(score); // undefined
//변수를 참조하는 코드 
var score; // 변수 선언문

//interpreter방식
//선언 전에 참조코드가 먼저 실행되므로 오류 발생?
//Nope why?
//변수 선언이 소스코드가 한줄씩 순차적으로 실행되는 시점(런타임)
//이 아니라 그 이전단계에서 먼저 실행되기 때문.

//변수 호이스팅(variable hoisting):
//변수 선언문이 코드의 선두로 끌어 올려진 것처럼 동작하는 
//자바스크립트 고유의 특징
//var, let, const, function, function*, class 키워드를 사용해서 선언하는 모든 식별자(변수, 함수, 클래스 등)는 호이스팅가능.
```



### #5 값의 할당 

> 변수에 값을 할당(assignment; 대입, 저장)할 때는 할당 연산자(=)를 사용한다. 할당 연산자는 우변의 값을 좌변의 변수에 할당한다.

```js
var score;  // 변수 선언
score = 80; // 값의 할당

//변수 선업과 값의 할당을 하나의 문(statement)으로 단축표현
var score = 80; // 변수 선언과 값의 할당
```

- 주의 사항

  > **변수 선언**은 소스코드가 순차적으로 실행되는 시점인
  > <u>런타임 이전에 먼저 실행</u>되지만 
  >
  > **값의 할당은** 소스코드가 순차적으로 실행되는 시점인 <u>런타임에 실행</u>

  ```js
  console.log(score); // undefined
  
  var score;  // ① 변수 선언 : 런타임 이전 실행
  score = 80; // ② 값의 할당 : 런타임에 실행
  
  console.log(score); // 80
  ```

  

- 주의 사항 2

  > 수에 값을 할당할 때는 이전 값 `undefined`가 저장되어 있던 메모리 공간을 지우고 그 메모리 공간에 할당 값 80을 새롭게 저장하는 것이 아니라 새로운 메모리 공간을 확보하고 그 곳에 할당 값 80을 저장하는 점에 주의

<img src="/Users/jeonsejin/Library/Application Support/typora-user-images/스크린샷 2020-11-17 오전 12.15.07.png" alt="스크린샷 2020-11-17 오전 12.15.07" style="zoom:50%;" /> 



### #6.값의 재할당

> 재할당이란?
> 이미 값이 할당되어 있는 변수에 새로운 값을 또다시 할당하는 것 
> 현재 변수에 저장된 값을 버리고 새로운 값을 저장하는 것 

```js
var score = 80; // 변수 선언과 값의 할당
score = 90;     // 값의 재할당
```

<img src="/Users/jeonsejin/Library/Application Support/typora-user-images/스크린샷 2020-11-17 오전 12.20.08.png" alt="스크린샷 2020-11-17 오전 12.20.08" style="zoom:50%;" /> 

```js
//현재 score 변수의 값 = 90 
//score변수 이전의 값 = undefined & 80
//어떤 식별자와도 연결되어 있지 않는 것을 의미
//불필요한 값들은 가비지 콜렉터에 의해 메모에서 자동해제
//단, 해제 시기 예측 불가
```

- garbage collector

  > 애플리케이션이 할당한 메모리공간을 주기적으로 검사하여 사용되고 있지않은 메모리를 해제(release)하는 기능
  >
  > > 더 이상 사용하고 있지 않는 메모리 
  > > = 어떤 식별자도 참조하지 않는 메모리 공간
  > > 메모리 누수(memory leak)방지 
  > >
  > > - 메모리 관리 방식
  > >
  > > | Unmanaged                                                    | Managed                                      |
  > > | ------------------------------------------------------------ | -------------------------------------------- |
  > > | 명시적으로 메모리 할당/해제하기 위해 malloc( ), free(  )같은 저수준 메모리 제어 기능 | 명시적으로 메모리를 할당하고 해제할 수 없음. |
  > > | 직접 제어 할 수 있음                                         | 직접제어할 수 없음                           |
  > >
  > > 

#### 상수란?

> 값을 재할당 할 수 없어서 변수에 저장된 값을 변경할 수 없는 것
> 한번 정해지면 변하지 않는 값
> 한번만 할당할 수 있는 변수 

```js
const keyword
//const를 사용해 선언한 변수는 재할당이 금지됨.
//주의 ) 반드시 상수만을 위해 사용하지는 않는다. 
```



### #7. 값의 교환

```js
var x = 1;
var y = 2;

// do something

console.log(x, y); // 2 1
```



### #8.식별자 네이밍 규칙

- 특수문자를 제외한 문자, 숫자, 언더스코어, 달러기호
- 단, 숫자로 시작하는 것은 허용하지 않는다.
- [예약어][프로그래밍 언어에서 사용되고 있거나 사용될 예정인 단어]는 식별자로 사용할 수 없다.
- 명명 규칙위반 하여 사용할 수 없다.

```js
var first-name; // SyntaxError: Unexpected token – (특수문자)
var 1st;        // SyntaxError: Invalid or unexpected token (숫자 첫번째)
var this;       // SyntaxError: Unexpected token this (예약어)
```

- 대소문자 구별한다.

```js
var firstname;
var firstName;
var FIRSTNAME;
//각각 별개의 변수
```

- 존재의 목적을 쉽게 이해할 수 있도록 명확히 표현해야 한다.
- 별도의 주석이 필요하다면 변수의 존재목적이 명확하지 않은 것

> naimg convention?

> 하나이상의 영어단어로 구성된 식별자를 만들 때 가독성 좋게 
> 단어를 한눈에 구분하기 위해 규정한 명명 규칙.
>
> ```js
> // 카멜 케이스 (camelCase)
> var firstName;
> 
> // 스네이크 케이스 (snake_case)
> var first_name;
> 
> // 파스칼 케이스 (PascalCase)
> var FirstName;
> 
> // 헝가리언 케이스 (typeHungarianCase)
> var strFirstName; // type + identifier
> var $elem = document.getElementById('myId'); // DOM 노드
> var observable$ = fromEvent(document, 'click'); // RxJS 옵저버블
> ```
>
> 

