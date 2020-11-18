# JAVAScript

### #1 JavaScript의 탄생배경

웹 페이지의 보조적인 기능을 수행하기 위해 브라우저에서 동작하는 경량 프로그래밍 언어를 도입 

> Mocha > LiveScript > JavaScript



### #2 JavaScript history

웹 페이지의 보조적인 기능을 수행하기 위한 한정적용도로 사용
대부분의 로직은 주로 웹 서버에서 실행되었고, 브라우저는 서버로부터 전달받은 HTML과 CSS를 단순히 렌더링하는 수준

> rendering ? 
> HTML, CSS, 자바스크립트로 작성된 문서를 해석해서 브라우저에 시각적으로 출력하는 것을 말한다. 때로는 서버에서 데이터를 HTML로 변환해서 브라우저에게 전달하는 과정(SSR; Server Side Rendering)을 가리키기도 한다



### #3 Ajax

자바스크립트를 이용해 서버와 브라우저가 **비동기(asynchronous)** 방식으로 데이터를 교환할 수 있는 통신 기능인 **Ajax(Asynchronous Javascript And XML)**가 XMLHttpRequest라는 이름으로 등장

> 페이지에서 변경할 필요가 없는 부분은 다시 렌더링하지 않고, 서버로부터 필요한 데이터만 전송받아 변경해야 하는 부분만 한정적으로 렌더링하는 방식



### #4 Node.js

구글 V8 자바스크립트 엔진으로 빌드된 자바스크립트 런타임 환경(runtime environment) 
브라우저 이외의 환경에서도 동작할 수 있도록 자바스크립트 엔진을 브라우저에서 독립시킨 자바스크립트 실행 환경



### #5 ECMAScript < JavaScript 

### <img src="/Users/jeonsejin/Library/Application Support/typora-user-images/스크린샷 2020-11-16 오후 5.58.04.png" alt="스크린샷 2020-11-16 오후 5.58.04" style="zoom:50%;" /> 

> ECMAScript

```js
//JS의 표준 사양 : ECMAScript 
//https://www.ecma-international.org/ecma-262/11.0/index.html#title 
//브라우저 & node.js 모두 돌아가는 것 
//JavaScript 엔진을 만들 때 참고해라는 뜻에서 제작된 것 
```

#### Web API

> 브라우저에서만 적용되는 것  
>
> ```js
> //example ) alert
> //https://developer.mozilla.org/ko/docs/Web/API
> ```

#### Host API

> node.js에서만 적용되는 것 
>
> ```js
> https://nodejs.org/dist/latest/docs/api/
> ```



### #6 JAVAScript 특징

##### (1) 자바스크립트?

> HTML, CSS와 함께 웹을 구성하는 요소 중 하나로 **웹 브라우저에서 동작하는 유일한 프로그래밍 언어**다



##### (2) Interpreter vs complier

- complier (번역가)  

> 처음부터 끝까지 통째로 기계어로 바꾸어 주는 것 

- interpreter (통역가)( Java default )

>  한줄씩 동시통역 하듯이 바꾸어 주는 것

<img src="/Users/jeonsejin/typoraimge/image0ㅇㅇㅇ.jpg" alt="image0ㅇㅇㅇ" style="zoom: 25%;" />  <img src="/Users/jeonsejin/typoraimge/image4.jpg" alt="image4" style="zoom:50%;" />