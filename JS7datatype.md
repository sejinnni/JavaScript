

# DataType

```js
Q) keyword?
A) 자바스크립트가 이미 정의되어 있는 것 
	 뭐를 만나면 뭐를 실행해라 > action이 정해져 있는 것 
```

```js
Q) property key?
A) 속성을 참조할 수 있는 이름 
```

```js
Q) Symbol type?
A)
//심벌값 생성 
var key = symbol('key');
//var key = 고유 symbol
//symbol('key') = symbol 설명

//객체 생성
var obj = { };
//빈 객체 생성

//유일무이한 symbol을 property key사용
obj[ key ] = 'value';
//빈 객체에 값을 대입한다.
console.log(obj[key]);
//value출력 한다.
```

