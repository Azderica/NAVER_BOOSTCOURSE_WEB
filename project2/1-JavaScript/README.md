# 네이버 부스트 코스 1주차

## JavaScript

### 자바스크립트 변수-연산자-타입

**자바스크립트의 버전**

- 자바스크립트 버전은 ECMAScript(줄여서ES)의 버전에 따라서 결정되고, 이를 자바스크립트 실행 엔진이 반영합니다.
- ES5, ES6(ES2015).. 이런 식으로 버전을 일컫습니다.
- 2018년을 중심으로 ES6를 지원하는 브라우저가 많아서 몇 년간 ES6 문법이 표준으로 쓰이고 있습니다.
- ES6는 ES5문법을 포함하고 있어 하위호환성 문제가 없습니다.
- 다만 **feature별로 지원하지 않는 브라우저가 있을 수 있어 조심**해야 합니다.

**변수**

변수는 `var, let, const` 로 선언할 수 있습니다.

어떤 것을 사용하는가에 의해서 scope, 즉 변수의 유효범위가 달라집니다.

ES6이전까지는 var를 사용해서 변수를 선언할 수 있습니다.

```js
var a = 2;
var a = "aaa";
var a = "aaa";
var a = true;
var a = [];
var a = {};
var a = undefined;
```

**연산자**

연산자 우선순위를 표현하기 위해서는 ()를 사용하면 됩니다.

수학연산자는 +,-,\*,/,%(나머지) 등이 있습니다.

그리고 논리 연산자, 관계연산자, 삼항연산자도 있습니다.

```js
//or 연산자 활용
const name = "crong";
const result = name || "codesquad";	// or을 이용하면 선언하기 편함
console.log(result);
var name = "";
var result = name || "codesquad";
console.log(result);
```

**연산자 - 삼항연산자**

간단한 비교와 값 할당은 삼항연산자를 사용할 수 있습니다.

```js
const data = 11;
const result = data > 10 ? "ok" : "fail";
console.log(result);
```

**연산자 - 비교연산자**

비교는 == 보다는 === 를 사용한다.

==로 인한 다양한 오류 상황이 있는데 아래 결과를 참고해봅시다.

```js
0 == false;
"" == false;
null == false;
0 == "0";
null == undefined;
```

**자바스크립트의 Type**

자바스크립트 타입에는 다양한 것이 존재합니다.

```js
> undefined, null, boolean, number, string, object, function, array, Date, RegExp
```

타입은 선언할 때가 아니고, 실행타임에 결정됩니다.

함수안에서의 파라미터나 변수는 실행될 때 그 타입이 결정됩니다.

타입을 체크하는 또렷한 방법은 없습니다.

정확하게는 toString.call 함수를 이용해서 그 결과를 매칭하곤 하는데, 문자, 숫자와 같은 자바스크립트 기본 타입은 'typeof' 키워드를 사용해서 체크할 수 있습니다.

배열은 타입을 체크하는 isArray함수가 표준으로 생겼습니다.

IE와 같은 구 브라우저를 사용해야 한다면 지원범위를 살펴보고 사용해야 합니다.

---

### 자바스크립트 비교-반복-문자열

**비교문**

if , else if, else 를 통해서 다양한 비교문을 사용할 수 있습니다. 

**분기 - switch** 

로직을 분기하기 위해서 if문 이외에도 switch 문을 통해서도 해결할 수 있습니다. 

**반복**
for 문이나 while문을 사용해서 반복문을 구현할 수 있습니다.

```javascript
function howMany(selectObject) {
  var numberSelected = 0;
  for (var i = 0; i < selectObject.options.length; i++) {
    if (selectObject.options[i].selected) {
      numberSelected++;
    }
  }
  return numberSelected;
}
```

배열의 경우 forEach와 같은 메서드도 있고, for-of를 통한 탐색도 자주 사용됩니다.

(for-in은 객체를 탐색할때 사용합니다)

forEach와 같은 메서드의 사용법이 익숙하지 않다면, 우선은 for문으로 배열을 탐색하는 것으로 충분합니다.

**문자열 처리**

자바스크립트의 문자와 문자열은 같은 타입으로 모두 문자열입니다.

```javascript
typeof "abc";  //string
typeof "a";    //string
typeof 'a';    //string. single quote도 사용가능.
```

문자열에 다양한 메서드가 있습니다.

```javascript
"ab:cd".split(":"); //["ab","cd"]
"ab:cd".replace(":", "$"); //"ab$cd"
" abcde  ".trim();  //"abcde"
```

---

### 자바스크립트 함수

**함수 - 함수의 선언**

**함수는 여러 개의 인자를 받아서, 그 결과를 출력합니다.** 

파라미터의 개수와 인자의 개수가 일치하지 않아도 오류가 나지 않습니다. 

만약, 파라미터 1개가 정의된 함수를 부를 때, 인자의 개수를 0개만 넣어 실행하면, 이미 정의된 파라미터(매개변수)는 undefined이라는 값을 갖게 됩니다.

이는 변수는 초기화됐지만, 값이 할당되지 않았기 때문입니다.

이를 한번 테스트해보세요.

```javascript
// 함수의 호출.
function printName(firstname) {
    var myname = "jisu";
    return myname + " " +  firstname;
}
```

위와 같은 형식의 함수 선언코드는 **함수선언문**이라고 합니다. 

**함수 - 함수표현식**

함수는 아래 printName과 같이 표현할 수도 있습니다.

이렇게 표현하면 함수선언문과 달리 선언과 호출순서에 따라서 정상적으로 함수가 실행되지 않을 수 있습니다.

```javascript
function test() { 
    console.log(printName()); 
    var printName = function() {
        return 'anonymouse';
    }
}

test();
//TypeError: printName is not a function
```

함수 표현식보다 함수 선언문을 더 자주 사용하지만, 어떤 코딩컨벤션에서는 **함수 표현식**을 권장하기도 합니다.

어떤 컨벤션을 갖던지 한가지만 정해서 사용하는 게 좋습니다.

**함수 - 표현식과 호이스팅**

앞선 코드에서, printName이 "printName이 is not defined" 이라고 오류가 나오지 않고, function이 아니라고 나온 이유는
printName이 실행되는 순간 'undefined'으로 지정됐기 때문입니다.

**자바스크립트 함수는 실행되기 전에 함수 안에 필요한 변수값들을 미리 다 모아서 선언**합니다.

함수 안에 있는 변수들을 모두 끌어올려서 선언한다고 해서, 이를 **hoisting**이라고 합니다.
(실제로 코드가 끌어올려지는 건 아니며<이 과정이 눈에 보이는 게 아니죠>, 자바스크립트 파서 내부적으로 그렇게 끌어올려서 처리하는 것입니다)

따라서 아래 코드 역시 함수를 값으로 가지지만 어쨌든 printName도 변수이므로 끌어올려지고, 값이 할당되기 전에 실행됐으므로 undefined가 할당된 상태입니다.

```javascript
printName(); //아직, printName이 undefined으로 할당된 상태다. 
var printName = function(){}
```

printName이라는 변수가 존재하고 아직 값이 할당되기 전이므로 printName에는 'undefined'이라는 기본 값이 할당된 셈입니다.

**함수 - 반환값과 undefined**

아래 함수의 반환값은 무엇일까요? 

```javascript
function printName(firstname) {
    var myname = "jisu";
    var result = myname + " " +  firstname;
}
```

정답은 undefined입니다.

자바스크립트 함수는 반드시 return값이 존재하며, 없을 때는 기본 반환값인 'undefined'가 반환됩니다.

자바스크립트에서는 void 타입이 없습니다.

**함수 - arguments 객체**

함수가 실행되면 그 안에는 arguments라는 특별한 지역변수가 자동으로 생성됩니다.

arguments의 타입은 객체 입니다.(console.log( typeof arguments) 로 확인해보세요!)

자바스크립트 함수는 선언한 파라미터보다 더 많은 인자를 보낼 수도 있습니다.

이때 넘어온 인자를 arguments로 배열의 형태로 하나씩 접근할 수가 있습니다.

arguments는 배열타입은 아닙니다.

따라서 배열의 메서드를 사용할 수가 없습니다.

```javascript
function a() {
 console.log(arguments);
}
a(1,2,3);
```

자바스크립트의 가변인자를 받아서 처리하는 함수를 만들때 등에서 arguments속성을 유용하게 사용할 수가 있습니다.

---

### 자바스크립트 함수 호출 스택

**함수 호출**

자바스크립트 함수 호출은 이렇게 불려집니다. 

이 함수를 실행해보세요.

run이 호출되고 그 다음에 printName이 호출됩니다.

```javascript
// 함수의 호출.
function printName(firstname) {
    var myname = "jisu";
    return myname + " ," +  firstname;
}

function run(firstname) {
   firstname = firstname || "Youn";
   var result = printName(firstname);
   console.log(result);
}
```

**함수호출과 stack**

아래 그림을 마우스로 클릭해서, 내용이 변경되는 것을 차분히 이해해보세요.

한 번에 보기 어렵다면 여러 번 돌려보며 이해해보세요. 

[![img](https://cphinf.pstatic.net/mooc/20180126_83/1516946077823AvIcy_GIF/2-1-4-1____.gif?type=w760)](https://www.edwith.org/boostcourse-web/lecture/16696/#)

- **함수 호출 스택** [출처](https://medium.com/@gaurav.pandvia/understanding-javascript-function-executions-tasks-event-loop-call-stack-more-part-1-5683dea1f5ec)

```javascript
function foo(b){
    var a = 5;
    return a * b + 10;
} 

function bar(x){
    var y = 3;
    return foo(x * y);
}

console.log(bar(6));
```

함수 호출 관계는 다음과 같습니다.

`bar() → foo()`

메모리에서는 우측의 Call Stack에서와같이 순서대로 쌓이게 됩니다.

bar 함수에서 foo를 호출한 후 foo 함수의 결과를 받아올 때까지 bar함수는 메모리 공간에서 사라지지 못하고 기다리고 있는 것이죠.

이를 당연히 생각할 수 있습니다.

foo의 경우에는 실행이 끝나고 return문이 실행되면 메모리 공간에서 사라집니다.

다시 말해서 Call Stack에서 없어지는 것이죠. 

call stack은 이렇게 동작하지만, 함수를 연속적으로 계속 호출하면 call stack이 꽉 차버리면서 더 실행되지 못하고 오류가 발생할 겁니다.

브라우저에서는 대부분 지정된 횟수만큼만 call stack을 쌓게 미리 설정해둔 경우가 많다고 합니다.

따라서 혹시 개발 중에 **Maximum call stack size exceeded** 오류를 발견해도 너무 놀라지 말고, 대처하도록 하세요.

 