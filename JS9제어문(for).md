# 제어문(control flow statement)

> [제어문][주어진 조건에 따라 코드블록을 실행(조건문)하거나 반복실행(반복문)할 때 사용한다.]
>
> > 코드 실행 흐름을 인위적으로 제어할 수 있다. 



## #1.블록문(block /compound statement)

> 0개 이상의 문을 중괄호로 묶은 것 = 코드 블록 (블록)

```js
//특징
1.자바스크립트는 블록문을 하나의 실행단위로 취급 
2.단독 사용가능 하나 제어문이나 함수를 정의할 때 사용하는 것(일반적)
2.자체 종결성을 갖고 있어서(self closing) 세미콜론을 붙이지 않는다.
//문의 종료를 의미하는 것 

// 블록문
{
  var foo = 10;
}

// 제어문
var x = 1;
if (x < 10) {
  x++;
}

// 함수 선언문
function sum(a, b) {
  return a + b;
}
```



## #2.조건문(conditional statement)

> 주어진 **조건식**의**' 평가 결과 '**에 따라 블록(블록문)의 실행을 결정한다.
> *조건식? : 불리언 값으로 평가될 수 있는 표현식
> if 문의 조건식은 불리언 값으로 평가되어야 한다. 

- ### 2-1.if...else문 

  > 주어진 조건식의 평가결과
  >  = **논리적 참 / 거짓**에 따라 **실행할 코드블록** 결정

  ```js
  if (조건식) {
    // 조건식이 참(true)이면 이 코드 블록이 실행된다.
  } else {
    // 조건식이 거짓(false)이면 이 코드 블록이 실행된다.
  }
  ```

  - #### **if...else문 특징**

  ```js
  1. 조건식을 추가하고 싶다면 "else if"를 사용한다.
  2. else if & else 문은 option
  3. if & else 문은 2번만 사용가능하지만 else if는 여러번 가능
  4. 코드 블록 내의 문이 하나뿐이라면 중괄호 생략가능 
  5. 삼항 조건 연산자로 바꿔 쓸 수 있다. 
  ```

  ```js
  //3번 특징
  if (조건식1) {
    // 조건식1이 참이면 이 코드 블록이 실행된다.
  } else if (조건식2) {
    // 조건식2가 참이면 이 코드 블록이 실행된다.
  } else {
    // 조건식1과 조건식2가 모두 거짓이면 이 코드 블록이 실행된다.
  }
  ```

  ```js
  //4번 특징
  var num = 2;
  var kind;
  
  if (num > 0)      kind = '양수';
  else if (num < 0) kind = '음수';
  else              kind = '영';
  
  console.log(kind); // 양수
  ```

  ```js
  //5번 특징 
  // x가 짝수이면 result 변수에 문자열 '짝수'를 할당하고, 홀수이면 문자열 '홀수'를 할당한다.
  var x = 2;
  var result;
  
  if (x % 2) { // 2 % 2는 0이다. 이때 0은 false로 암묵적 강제 변환된다.
    result = '홀수';
  } else {
    result = '짝수';
  }
  
  console.log(result); // 짝수
  
  //삼항 조건 연산자 
  var x = 2;
  
  // 0은 false로 취급된다.
  var result = x % 2 ? '홀수' : '짝수';
  console.log(result); // 짝수
  
  //경우의 수 3가지 
  var num = 2;
  
  // 0은 false로 취급된다.
  var kind = num ? (num > 0 ? '양수' : '음수') : '영';
  
  console.log(kind); // 양수
  ```

  |                | if...else | 삼항조건 연산자 |
  | -------------- | --------- | --------------- |
  | 표현식         | 아닌 문   | 표현식인 문     |
  | 값처럼         | 사용 X    | 사용 O          |
  | 변수에         | 할당 X    | 할당 O          |
  | 가독성(여러줄) | V         |                 |

  ### 2-2.Switch문

  > 주어진 표현식을 평가 
  > = > 값과 일피하는 표현식을 갖는 case문으로 실행 흐름을 옮긴다.

  > *case 문? 
  > 상황(case)를 의미하는 표현식을 지정하고 콜론으로 마친 후, 
  > 실행 할 문들을 위치 시킨다.

  - #### **switch문 특징**

    ```js
    1. 표현식과 일치하는 case 문이 없다면 실행순서는 
    	 default문으로 이동한다.	
    		-default 문은 선택사항
    2. 문자열 값이나 숫자값으로 평가되는 경우가 많다. 
    3. 폴스루(fall through)('BREAK 문')
    4. break 문이 없다면 실행흐름이 연이어 이동한다.
    5. default 문에는 break 문을 생략한다. 
    ```

    ```js
    switch (표현식) {
      case 표현식1:
        switch 문의 표현식과 표현식1이 일치하면 실행될 문;
        break;
      case 표현식2:
        switch 문의 표현식과 표현식2가 일치하면 실행될 문;
        break;
      default:
        switch 문의 표현식과 일치하는 표현식을 갖는 case 문이 없을 때 실행될 문;
    }
    ```

    

    - **폴 스루 ( fall through )**

      > **Break 문을 생략한 것**
      > =>문을 실행한 후 switch 문을 탈출하지 않고  switch 문이 끝날 때까지 이후의  모든 case 문과 default 문을 실행
      >
      > A) case문에 해당하는 문의 마지막에 [**break문**][코드블록에서 탈출하는 역할]을 사용X

      ```js
      // 월을 영어로 변환한다. (11 → 'November')
      var month = 11;
      var monthName;
      
      switch (month) {
        case 1: monthName = 'January';
          //break;
        case 2: monthName = 'February';
          //break;
        case 3: monthName = 'March';
        case 4: monthName = 'April';
        case 5: monthName = 'May';
        case 6: monthName = 'June';
        case 7: monthName = 'July';
        case 8: monthName = 'August';
        case 9: monthName = 'September';
        case 10: monthName = 'October';
        case 11: monthName = 'November';
          //break;
        case 12: monthName = 'December';
      '  default: monthName = 'Invalid month';'
          /break 문 생략 
      }
      
      console.log(monthName); //' Invalid month'
      
      //November 가 할당된 후 문을 탈출 하지 않고 재할당 지속
      ```

    - break문을 생략한 폴스루가 유용한 경우 

      > 여러 개의 case 문을 하나의 조건으로 사용할 수 있다. 
      >
      > ```js
      > var year = 2000; 
      > // 2000년은 윤년으로 2월이 29일이다.
      > var month = 2;
      > var days = 0;
      > 
      > switch (month) {
      > case 1: case 3: case 5: case 7: case 8: case 10: case 12:
      >     days = 31;
      >     break;
      > ```

| 조건문의 차이점          | if...else      | switch              |
| ------------------------ | -------------- | ------------------- |
|                          | 조건식         | 표현식              |
| 평가                     | 불리언 값      | 문자열  값/ 숫자 값 |
| 실행할 코드블록 결정기준 | 논리적 참/거짓 | 다양한 상황(case)   |
|                          |                | C-family언어 지원   |



## #3.반복문(loop statement)

> 조건식의 평가결과가 **"true"**인 경우 코드블록을 실행한다. 
> 조건식이 거짓일 때 까지 평가 > true > 평가 > true > 평가 > false 반복

<contents>

```js
3-1. for 문
3-2. while 문
3-3. Do...while 문
3-4. Break 문
3-5. Continue 문
```



### 3-1.for 문

```js
1.조건식이 거짓( ' false ' )으로 평가될 때 까지 코드블록 반복 실행
	-무한루프 개념 
2.중첩 for 문 : for 문 내에 for 문을 중첩해 사용할 수 있다. 
```

```js
//특징 1
for (변수 선언문 또는 할당문; 조건식; 증감식) {
  조건식이 참(true)인 경우 반복 실행될 문;
}

//변수 선언문, 조건식, 증감식 모두 옵션이므로 반드시 사용할 필요는 없다.
//하지만 어떤식도 선언하지않으면 무한루프(코드 블록 무한반복실행하는 문)됨
// 무한루프
for (;;) { ... }
```

```js
//i: iteration : 반복을 의미한다.
//for문의 변수선언문의 변수이름으로 일반적으로 사용

for (var i = 0; i < 2; i++) {
  console.log(i); 
}
//0
//1 
```

![스크린샷 2020-11-19 오전 10.40.21](/Users/jeonsejin/Desktop/스크린샷 2020-11-19 오전 10.40.21.png) 

```js
Q) 조건식을 실행한 후 왜 증감식을 실행하지 않고 코드블록으로 
   실행흐름이 이동하는 건가요?     
A) 순차적으로 코드블록을 실행해야 값을 나온후 다시 조건식을 평가하는 것이
	 반복문의 특징입니다. 그 사이에 증감문이 추가된 것 뿐입니다. 
   그러므로 코드블록 실행 후 증감식을 실행하는 것이 옳습니다.  
```

```js
//특징 2 이중중첩 for 문 
for (var i = 1; i <= 6; i++) {
  for (var j = 1; j <= 6; j++) {
    if (i + j === 6) console.log(`[${i}, ${j}]`);
    //조건식 
  }
}
//
[1, 5]
[2, 4]
[3, 3]
[4, 2]
[5, 1]
```



### 3-2. while문

```js
1. 주어진 조건식의 평가결과가 참이면(true), 코드블록 반복 실행
	 -무한루프 : 언제나 참이면 
2. 조건문의 평가 결과가 거짓(false)면, 코드블록 실행하지 않고 종료 
3. 조건식의 평가결과가 불리언 값이 아니면, 강제로 불리언 값으로 변환하여 
 	 논리적 참, 거짓을 구별한다. 
```

|          | for 문                | while 문               |
| -------- | --------------------- | ---------------------- |
| 반복횟수 | 명확할 때 사용        | 불명확할 때 사용       |
|          | 일정횟수만큼 반복실행 | 반복횟수를 알지 못할때 |
| 이중중첩 | O                     | O                      |

```js
Q) for 문도 while 문과 같이 조건식의 평가결과가 불리언 값이 아니면,
   강제로 불리언 값으로 변환하여 논리적 참, 거짓을 구별할 수 있나요?     
A) 네!
```

```js
//무한루프 탈출 방법
//코드 블록내에 if 문으로 탈출조건을 만들고 break 문으로 코드블록 탈출
var count = 0;

// 무한루프
while (true) {
  console.log(count);
  count++;
  // count가 3이면 코드 블록을 탈출한다.
  if (count === 3) break;
} // 0 1 2
```



### 3-3.do... while문

```js
1. 코드블록 먼저 실행하고 조건식을 평가한다. 
	> 코드 블록 무조건 한번 이상 실행된다. 
```

```js
var count = 0;

// count가 3보다 작을 때까지 코드 블록을 계속 반복 실행한다.
do {
  console.log(count);
  count++;
} while (count < 3); // 0 1 2
```



### 3-4.break 문

> 레이블 문, 반복문, switch 문 의 **"코드블록"** 을 탈출 하는 것 
> 레이블 문, 반복문, switch 문 의 "코드블록" **외에** break문 사용하면 
> **"syntaxError"(문법에러)** 발생한다. 

```js
//조건문에 break 문 사용했기 때문에 문법 에러 발생 
if (true) {
  break; // Uncaught SyntaxError: Illegal break statement
}
```

- [레이블 문 ][식별자가 붙은 문 , label statement]

```js
//특징
1.행순서를 제어하는데 사용한다. 
2.switch 문 & case 문 & default 문 < label 문 
3.레이블 문 탈출하려면 break 문에 레이블 식별자를 지정한다. 
4.중첩된 for문에서 외부for문 탈출할 때 사용한다.(**)
5.중첩된 외부 for 문으로 탈출할 때 제외하고 권장하지 않는다.
	-	프로그램의 흐름이 복잡해져서 가독성이 나빠진다.
  - 오류발생시킬 가능성이 높아진다. 
```

```js
// foo라는 레이블 식별자가 붙은 레이블 문
foo: console.log('foo');
```

```js
// foo라는 식별자가 붙은 레이블 블록문
foo: {
  console.log(1);
  break foo; // foo 레이블 블록문을 탈출한다.
  console.log(2);
}

console.log('Done!');
```

```js
//특징 4
//내부 for문에서 break문 실행 > 외부 for 문으로 진입 
//외부 for문에서 탈출하려면 레이블 문 사용
outer: for (var i = 0; i < 3; i++) {
  for (var j = 0; j < 3; j++) {
// i + j === 3이면 outer라는 식별자가 붙은 레이블 for 문을 탈출.
    if (i + j === 3) break outer;
    console.log(`inner [${i}, ${j}]`);
  }
}
```

- switch 문 & 반복문 에서 "break 문"

  > 레이블 문과는 다르게 식별자를 정하지 않는다. 
  > 불피요한 반복을 줄여주어 유용하다. 



### 3-5.continue 문

```js
1.반복문의 코드 블록 실행을 현 시점에서 중단하고 반복문의 증감식으로 
	실행흐름을 이동시킨다. (vs for/while/do...while 문과 차이점)
2.break 문처럼 반복문을 탈출하지는 않는다. 
```

```js
var string = 'Hello World.';
var search = 'l';
var count = 0;

// 문자열은 유사배열이므로 for 문으로 순회할 수 있다.
for (var i = 0; i < string.length; i++) {
  // 'l'이 아니면 현 지점에서 실행을 중단하고 반복문의 증감식으로 이동한다.
  if (string[i] !== search) continue;
  count++; // continue 문이 실행되면 이 문은 실행되지 않는다.
}

console.log(count); // 3

// 참고로 String.prototype.match 메서드를 
//사용해도 같은 동작을 한다.
const regexp = new RegExp(search, 'g');
console.log(string.match(regexp).length); // 3
```

<img src="/Users/jeonsejin/typoraimge/image0.jpg" alt="image0" style="zoom:50%;" /> 