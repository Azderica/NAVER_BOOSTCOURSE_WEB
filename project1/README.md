# 네이버 부스트 코스 1주차

## Web개발의 이해

### 웹 관련 인기 언어

* Python : 프로그래밍 입문자가 읽기 쉽고 적은 코드를 사용, 웹사이트 개바에서도 많이 사용됨
* PHP : 웹의 80% 이상이 PHP로 만들어졌음. 그만큼 PHP는 웹 개발에서 많이 사용됨
* JavaScript : 프론트엔드 개발자라면 반드시 알아야하는 언어
* JAVA : 엔터프라이즈 소프트웨어 환경에 잘맞는 언어. 큰 규모의 소프트웨어 개발에 자바언어가 많이 사용됨
* Ruby : 빠른 개발에 널리 사용되며, 단순함과 세련된 웹 어플리케이션을 만들 수 있음 

#### HTTP

> 서버와 클라이언트가 인터넷상에서 데이터를 주고받기 위한 프로토콜(protocol)

##### HTTP 작동방식

* 서버/클라이언트 모델을 따름
* 장점
  * 불특정 다수를 대상으로 하는 서비스에 적합
  * 클라이언트와 서버가 계속 연결된 형태가 아니기 때문에 많은 요청과 응답을 처리할 수 있음
* 단점
  * 연결을 끊어서 클라이언트의 이전 상황을 알 수 없음
  * 이러한 특징을 무상태(Stateless)라고 말한다.
  * 이를 해결하기 위해 Cookie와 같은 기술을 사용한다.

##### URL(Uniform Resourcde Locator)

* 인터넷 상의 자원의 위치
* 특정 웹 서버의 특정 파일에 접근하기 위한 경로 혹은 주소

 ![HTTP](https://cphinf.pstatic.net/mooc/20180119_25/1516354290022wUY3x_PNG/http_-_.PNG)

##### HTTP 특징

* 요청 메서드 : GET, PUT, POST, PUSH, OPTIONS 등의 요청 방식
  * GET : 정보를 요청하기 위해 사용 - SELECT
  * POST : 정보를 밀어넣기 위해서 사용 - INSERT
  * PUT : 정보를 업데이트하기 위해서 사용 - UPDATE
  * DELETE : 정보를 삭제하기 위해서 사용 - DELETE
  * HEAD : HTTP의 헤더 정보만 요청, 자원 존재 유무나 서버 문제를 확인
  * OPTIONS : 웹 서버가 지원하는 메소드의 종류를 요청
  * TRACE : 클라이언트의 요청을 그대로 반환. echo 서비스로 서버 상태를 확인하기 위한 목적으로 주로 사용
* 요청 URI : 요청하는 자원의 위치를 명시
* HTTP 프토토콜 버전 : 웹 브라우저가 사용하는 프로토콜 버전



### 웹 Front-End 와 웹 Back-End

#### 웹프론트엔드

> 사용자에게 웹을 통해 다양한 콘텐츠를 제공하고 사용자의 요청에 반응하여 동작한다

##### 웹프론트엔드의 역할

* **HTML** : 웹콘텐츠를 잘 부여주기 위해 구조를 만들어야한다 
* **CSS** : 적잘한 배치와 일관된 디자인 등을 제공해야 합니다
* **JavaScript** : 사용자 요청을 잘 반영해야함



#### 백엔드

> 백엔드는 정보를 처리하고 저장하며, 요청에 따라 정보를 내려주는 역할을 한다. 상품 정보를 가지고 있고, 주문을 받아서 저장하고 사용자가 관심있어 하는 상품을 골라주는 역할

##### 백 엔드 개발자가 알아야 할 것들

* 프로그래밍 언어(JAVA, Python, PHP, JavaScript 등)
* 웹의 동작 원리
* 알고리즘(algorithm), 자료구조 등 프로그래밍 기반 지식
* 운영체제, 네트워크 등에 대한 이해
* 프레임워크에 대한 이해(ex. Spring)
* DBMS에 대한 이해와 사용방법(예: MySQL, Oracle 등)



### Browser의 동작

[Browser 동작 원리 원본](https://www.html5rocks.com/en/tutorials/internals/howbrowserswork/)

[Browser 동작 번역](https://d2.naver.com/helloworld/59361)

**Browser component**

![Browser componenets](https://d2.naver.com/content/images/2015/06/helloworld-59361-1.png)



**Rendering engine basic flow**

![Rendering engine basic flow](https://d2.naver.com/content/images/2015/06/helloworld-59361-2.png)


**Main flow exmples**

![Main flow examples](https://d2.naver.com/content/images/2015/06/helloworld-59361-3.png)



* 크로미움
  * V8 + Blink을 포함한 구글 브라우저 오픈소스 애플리케이션
  * 크롬
  * 렌더링 엔진으로 Blink를 (webkit에서 fork된)  사용

> DOM(Document Object Model)



##### 렌더링 엔진

요청 받은 내용을 브라우저 화면에 표시하는 일



##### HTML 파서

HTML 파서는 HTML 마크업을 파싱 트리로 변환한다



**CSS 파서**

![CSS TREE](https://d2.naver.com/content/images/2015/06/helloworld-59361-12.png)



**렌더 트리**

![렌더 트리](https://d2.naver.com/content/images/2015/06/helloworld-59361-13.png)



### 브라우저에서의 웹개발

#### HTML 문서구조

* HTML은 html이라는 태그로 시작해 html태그로 끝난다
* head은 문서에 대한 정보를 보여준다
* body는 화면에 표현될 div 등을 보여준다
* HTML은 계층적이다
* HTML은 tag를 사용해서 표현한다
* JavaScript와 CSS가 html 안에 여기저기 존재한다

JavaScript는 보통 아래에 위치하는 것이 좋다.


### 웹서버

* 웹 서버는 소프트웨어(SW)을 보통 말하지만, 웹 서버 소프트웨어가 동작하는 컴퓨터를 말함
* 웹 서버의 가장 중요한 기능은 클라이언트(Client)가 요청하는 HTML문서나 각종 리소스(Resource)를 전달하는 것
* 웹 브라우저나 웹 크롤러가 요청하는 리소스는 컴퓨터에 저장되어 있는 정적 (static)인 데이터이거나 동적인 결과가 될 수 있음

**프로토콜** : 규약

#### 웹 서버 소프트웨어의 종류

* 가장 많이 사용하는 웹 서버는 Apache, Nginx, Microsoft IIS
* **Apache** 웹 서버는 Apache Software Found에서 개발한 웹서버로 오픈소스 소프트웨어(Open-source Software)이며, 거의 대부분 운영체에서 설치 및 사용 가능
* **Ngix**는 **차세대 웹서버**로 불리며 더 **적은 자원으로 더 빠르게 데이터를 서비스**하는 것을 목적으로 만들어진 서버이며 Apach웹 서버와 마찬가지로 오픈소스 소프트웨어

웹 서버 시장 점유율 => Apache, **nginx(성장 중)**



### WAS(Web Application Server)

WAS는 일종의 미들웨어로 웹 클라이언트(보통 웹 브라우저)의 요청 중 웹 애플리케이션이 동작하도록 지원하는 목적을 가짐

![WAS](https://cphinf.pstatic.net/mooc/20180122_270/1516606715302CWRJG_PNG/1_1_7_was.PNG)

##### WAS의 중요 기능

* 프로그램 실행 환경과 데이터베이스 접속 기능 제공
* 여러 개의 트랜잭션(논리적인 작업단위)을 관리
* 업무를 처리하는 비즈니스 로직을 수행
* 웹서버의 기능도 기본적으로 제공
* 프로그램의 동적인 결과를 웹 브라우저에게 전달

웹서버를 WAS 앞단에서 동작하도록 설계하는 경우가 대용량 웹 어플리케이션에서는 자주 있는 케이스

#### 클라이언트/서버 구조

클라이언트(Client)는 서비스(Service)를 제공하는 서버(Server)에게 정보를 요청하여 응답 받은 결과를 사용

#### DBMS(DataBase Management System)

다수의 사용자가 데이터베이스 내의 데이터에 접근할 수 있도록 해주는 소프트웨어. 

![DBMS](https://cphinf.pstatic.net/mooc/20180122_74/15166087526093WS9P_PNG/1_1_7_DBMS.PNG)

#### 미들웨어 (MiddleWare)

클라이언트 쪽에 비즈니스 로직이 많을 경우, 클라이언트 관리로 인해 비용이 많이 발생하는 문제가 있다. 비지니스 로직을 클라이언트와 DBMS사이의 DBMS사이의 미들웨어 서버에서 동작하도록 함으로써 클라이언트는 입력과 출력을 담당한다.

![미들웨어](https://cphinf.pstatic.net/mooc/20180122_267/1516608805247GN2hK_PNG/1_1_7_.PNG)

#### 웹 서버 vs WAS

* WAS도 보통 자체적으로 웹 서버 기능을 내장하고 있음
* 현재는 WAS가 가지고 잇는 웹 서버도 정적인 콘텐츠를 처리하는데 성능상 큰 차이가 없음
* 규모가 커질수록 웹 서버와 WAS를 분리 가능
* 자원 이용의 효율성 및 장애 극복, 배포 및 유지보수의 편의성을 위해 웹서버와 WAS를 대체로 분리한다.

#### 톰캣 버전별 차이점

java와 서블릿의 버전이 다름.

웹서버 : 정적 / WAS : 동적
과거에는 아파치 + 톰캣 / 현재는 톰캣
아파치는 WAS가 가볍기 때문에 WAS에서 문제가 생겼을 때 재시작하는데 아파치가 이를 지원해주는 역할



## HTML

### HTML Tags

HTML의 태그는 그 의미에 맞쳐서 사용해야한다.

> 링크, 이미지, 목록, 제목 등등
>
> anchor, img, ul/li, heading, p, div 등이 주로 쓰인다.

```html
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>JS Bin</title>
  </head>
  <body>
    <div>
      <h1>
        반갑습니다.
      </h1>
      여기 여러분들이 좋아하는 과일이 있어요.
    	<ul>
     	 <li><a href="http://www.apple.com">사과</a></li>
     	 <li>사과</li>
     	 <li>메론</li>
     	 <li>귤</li>
    	</ul>
    </div>
  </body>
</html>
```

### HTML Layout 태그

레이아웃이란 배치라는 뜻

**레이아웃을 위한 태그** 

> header, section, nav, footer, aside

![HTML5 layout tag](https://cphinf.pstatic.net/mooc/20171231_41/15146999078486r8Pv_JPEG/5086.HTML5PageLayout_2.jpg)

최신 브라우저가 많은  모바일 브라우저의 경우에는 footer을 써도 좋다.(데스크톱 환경에서는 글쎄) div랑 사실 똑같다.

```html
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>JS Bin</title>
  </head>
  <body>
    <header>header</header>
    <nav>
      <ul>
        <li>home</li>
        <li>news</li>
        <li>sports</li>
      </ul>
    </nav>
    <aside>
      <ul>
        <li>1</li>
        <li>2</li>
        <li>3</li>
      </ul>
    </aside>
    <footer>
      footer
    </footer>
  </body>
</html>
```

일반적으로 데스크탑에서는 header나 footer을 쓰지않고, div롤 쓰지만 클래스 명을 이처럼 짓고 모바일 환경에서는 많이 쓴다.

### HTML 구조설계

![html structure design](https://webstyleguide.com/wsg3/figures/6-page-structure/6-1-700.jpg)

핵심은 큰 구조 부터 설계하는 것이다. 그 후 상황에 맞는 태그를 쓰며 점점 안으로 좁혀가는 것이 개발 단계에서 유리하다.

div를 너무 많이 쓰지 않는 것이 좋다.



```html
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>JS Bin</title>
  </head>
  <body>
    <header>
      <h1>Company Name</h1>
      <img src="..." alt="logo">
    </header>
    
    <div>
      <nav>
        <ul>
          <li>Home</li>
          <li>Home</li>
          <li>About</li>
          <li>Map</li>
        </ul>
      </nav>
    </div>
    
    <div>
      <ul>
        <li>
          <h3>What we do</h3>
          <div>text 1</div>
        </li>
        <li>
          <h3>What we do</h3>
          <div>text 2</div>
        </li>
        <li>
          <h3>What we do</h3>
          <div>text 3</div>
        </li>
      </ul>
    </div>
    <footer>
      <span>Copyright @codesquad</span>
    </footer>
  </body>
</html>
```

간단한 예시 코드

### class와 id 속성

하위 클래스를 가지는 wrapper 역할을 알고, 아래의 영역을 커버하는 class이름을 잘 생각하기

#### ID

* 고유한 속성으로 한 HTML 문서에 하나만 사용 가능
* 고유한 ID 값이 있으면 하나하나에 특별한 제어를 할 수 있으며 검색에도 용이

#### Class

* 하나의 HTML문서 안에 중복해서 사용 가능
* 하나의 태크에 여러 개의 다른 class 이름을 공백을 기준으로 나열 가능
* 홈페이지 전체적인 스타일을 일관성 있게 지정하기 위해는 class 사용이 필수적

이렇게 구분할 수 있지만, 회사마다 어떠한 약속(convention)을 만들어서 자신들만의 규칙을 사용.

> ex) ID사용을 금하거나 class로만 사용하는 경우가 존재



#### Q. Class name을 잘 설정하는 방법은?

**BEM**, 알아보기 쉬워야 유지보수가 쉬움

**BEM(Block Element Modifier)**은 CSS Architecture의 하나. 

1. **Block**(전체를 감싸고 있는 블럭 요소)

* 독립적으로 의미가 있는 컴포넌트를 의미

``` html
<div class="block"> ... </div>
```

* Header, footer, nav, main 등의 컨텐츠 영역을 block으로 간주할 수 있음
* 더 구체적으로 본다면 header block은 logo block, search form block, authorization block을 포함할 수 있음

![Block 예시](https://junwoo45.github.io/img/css_architecture3.png)

* block은 클래스의 어근을 형성하고 항상 맨 앞에 위치한다



2. **Element**

* 독립적으로는 의미가 없으며 Block에 붙어서 사용되는 컴포넌트

```html
<div class="block">
  <span class="block__element">...</span>
</div>
```

* element는 block이 포함하고 있는 한 조각
* 예를 들어 위에서 보았던 block이미지에서, menu item은 menu block 바깥에서는 사용될 수 없다. 따라서 각각의 메뉴아이템은 element이다.

![Element 예시](https://junwoo45.github.io/img/css_architecture4.png)

* 두개의 **underscore로** 연결하여 블럭 다음에 위치 시킨다.

```css
.block__element {
	display: none;
}
.header__logo {
  property: value;
}

.header__tagline {
  property: value;
}

.header__navigation {
  property: value;
}
```



3. **Modifiers**

* modifier는 block또는 element의 속성

  이 속성은 block이나 element의 외관이나 상태를 변화

  기본적으로, class 명은 반복하여 재사용할 수 있게 하기 위해 존재

  특정 요소의 스타일을 수정해야할 필요가 있을때 modifier를 활용하게 된다.

  이때, element나 block다음에 두개의 하이픈 '--'을 추가하여 modifier를 표시한다.

```css
.block__element--modifier {
  display: none;
}
```

* 다음처럼 focuesed된 tab3를 modifiers라고 볼 수 있다.

![modifier 예시](https://junwoo45.github.io/img/css_architecture5.png)

* 다른 예시, 아래와 같은 버튼을 만드는 경우

![버튼 예시](https://junwoo45.github.io/img/css_architecture2.jpeg)

```html
<button class="button">
  Normal button
</button>
<button class="button button--state-success">
  Success button
</button>
<button class="button button--state-danger">
  Danger button
</button>
```

```css
.button {
  display: inline-block;
	border-radius: 3px;
	padding: 7px 12px;
	border: 1px solid #D5D5D5;
	background-image: linear-gradient(#EEE, #DDD);
	font: 700 13px/18px Helvetica, arial;
}
.button--state-success {
  color: #FFF;
	background: #569E3D linear-gradient(#79D858, #569E3D) repeat-x;
}
.button--state-danger {
  color: #900;
}
```

와 같이 나타낼 수 있다.



#### Q. data속성을 사용하는 이유는?

html이 발전하면서 새롭게 추가된 기능으로 화면에 안보이게 추가정보를 엘리멘트에 담을 수 있다

- JS에서 dataset객체를 이용해 data-뒤의 이름을 불러 속성 값을 호출/변경할 수 있다.
- CSS에서도 특성 data-속성값 선택자를 통해 스타일을 바꿀 수 있다.

그러나 접근을 따로 할 수 없으므로 검색 크롤러와 같이 접근이 필요한 정보는 넣지않기



## CSS

### CSS 선언방법

```css
span {
  color : red;
}
```

구성 : span(**selector**, 선택자), color(**property**), red(**value**)

#### style을 HTML페이지에 적용하는 3가지 방법

1. inline

HTML태그 안에 적용.

```html
<p style="border:1px solid gray;color:red;font-size:2em;">
```

2. internal

style 태그로 지정. 구조와 스타일이 섞이게 되므로 유지보수가 어려움. 별도의 CSS파일을 관리하지 않아도 되며 서버에 CSS파일을 부르기 위해 별도의 브라우저가 요청을 보낼필요가 없음

```html
<style>
p  {
  font-size : 2em;
  border:1px solid gray;
  color: red;
}
</style>
```

3. external

외부파일 (.css)로 지정하는 방식이다. CSS 코드가 짧지 않는한 가급적 이 방법이 가장 좋다. 현업에서는 여러개의 CSS 파일로 분리하고 이를 합쳐서 서비스에서 사용

```html
<head>
	<link rel="stylesheet" href="style.css">
</head>
```

4. 우선순위

Inline > internal = external, 우선순위가 동등. 겹치는 경우는 나중에 선언된 속성이 반영됨

#### Q. javascript로 동적으로 css코드 수정방법은?

Id 또는 class를 통해 css 코드 수정이 가능

#### Q. google의 css?

inline은 거의 쓰지 않고 일반적으로는 internal이나 external을 주로 사용



### 상속과 우선순위 결정

일반적으로 css 속성은 하위에도 상속된다. 단 **box-model**이라 불리는 속성들(width, height, margin, padding, border) 등은 상속이 되지 않는다.

```css
#a{
 color : red;
}

.b{
 color : blue;
}

div{
 color : green;
}
```

위의 경우 **id, class, element 순으로 우선순위**를 가진다.

id는 클래스보다 우선되고, 클래스는 엘리먼트보다 우선된다. CSS의 이러한 특징을  **캐스캐이딩**이라 하며, id인 a의 색상이 적용된다.

#### 선언방식에 따른 차이

같은 선택자(selector)라면 나중에 선언한 것이 반영. 선택자의 표현이 구체적인것이 있다면 먼저 적용

- body > span (O)
- span (X)



### CSS Selector

CSS Selector란 HTML의 요소를 tag, id, html 태그 속성 등을 통해 쉽게 찾아주는 방법

**element에 style 지정을 위한 3가지 기본 선택자**

* tag

```css
<style>
     span {
       color : red;
     }
</style>
```

* Id

```html
<style>
     #spantag {
       color : red;
     }
</style>

<body>
     <span id="spantag"> HELLO World! </span>
</body>
```

* class

```html
<style>
     .spanClass {
     color : red
     }
</style>

<body>
    <span class="spanClass"> HELLO World! </span>
</body>
```

 

#### CSS Selector의 다양한 활용

* id, class 요소 선택자와 함께 활용

```css
#myid { color : red }
div.myclassname { color : red }
```

* 그룹 선택 (여러 개의 셀렉터에 같은 style을 적용해야 한다면)

```css
h1, span, div { color : red }
h1, span, div#id { color : red }
h1.span, div.classname { color : red }
```

* **요소 선택 (공백)** : 자손요소
* 아래 모든 span태그에 red 색상이 적용됨

```html
<div id="jisu">
  <div>
    <span> span tag </span>
  </div>
  <span> span tag 2 </span>
</div>
```

```css
#jisu span { color : red }
```

- **자식 선택 (>)** : 자식은 바로 하위엘리먼트를 가리킵니다.
- 아래는 span tag 2만 red 색상이 적용됩니다.

```html
<div id="jisu">
  <div>
    <span> span tag </span>
  </div>
  <span> span tag 2 </span>
</div>
```

```css
#jisu > span { color : red }
```

- n번째 자식요소를 선택합니다. (nth-child)
- 첫번째 단락에 red 색상이 적용됩니다.

```html
<div id="jisu">
  <h2>단락 선택</h2>
  <p>첫번째 단락입니다</p>
  <p>두번째 단락입니다</p>
  <p>세번째 단락입니다</p>
  <p>네번째 단락입니다</p>
</div>
```

```css
#jisu > p:nth-child(2) { color : red }
```

 

#### nth-child와 nth-of-type의 차이점?

* nth-of-type : 같은 태그의 n번째를 찾아서 적용

* nth-child : 태그 상관 없이 n번째를 찾아서 적용 (자식 태그)



### CSS 기본 Style 변경

CSS style 적용은 글자색, 배경색 등이 가장 자주 사용되는 것들입니다.

이런 속성은 위치 값과 크기를 지정하는 것과 달리, 색상 위주로 값을 부여합니다.

색상 관련 값은 다양한 색을 일관된 방법으로 표현하기 위해 주로 16진수 표기법을 사용합니다.

**font 색상 변경**

- color : red;
- color : rgba(255, 0, 0, 0.5);
- color : #ff0000;  //16진수 표기법으로 가장 많이 사용되는 방법이죠.

**font 사이즈 변경**

- font-size : 16px;
- font-size : 1em;
  - em은 부모에게 상속받은 크기의 상대적인 값.

**배경색** 

- background-color : #ff0;
- background-image, position, repeat 등의 속성이 있습니다.
- background : #0000ff url(“.../gif”) no-repeat center top; //한 줄로 정의도 가능

**글씨체/글꼴**

- font-family:"Gulim";
- font-family : monospace;



#### 웹 폰트

웹폰트는 브라우저에서 기본으로 지원하지 않는 폰트를 웹으로부터 다운로드 받아 사용할 수 있는 방법입니다.

다양하고 예쁜 폰트들을 웹폰트로 사용할 수 있긴 하지만 다운로드를 받아야 한다는 단점이 있습니다.

다운로드 시간이 오래 걸리게 되면 화면에 노출되는 시간이 느려져 오히려 사용자에게 불편함을 느끼게 할 수 있는 것 입니다.

또한 다양한 해상도에서 깨지는 문제도 발생할 수 있습니다.

웹폰트는 수많은 종류가 있습니다.

대표적으로 구글 웹폰트가 있으며 최근에는 다양한 크기에서 품질을 유지하는 벡터 방식의 아이콘 웹폰트도 등장했습니다.

(unicode영역 중 Private Use Area (PUA) 영역을 활용해서 제작)

또한 웹폰트 방식말고, 기본 unicode를 사용해서 간단한 아이콘을 표현하는 것도 가능합니다.

아래 unicode를 사용한 HTML 코드를 참고하세요.

```html
 <div> 안녕하세요 &#x263a;</div> //☺  웹 화면에는 웃음 표시가 표현되는 코드입니다.
```



### Element가 배치되는 방법(CSS layout)

#### 엘리먼트가 배치되는 방식

엘리먼트를 화면에 배치하는 것을 **layout 작업**이라고도 하고, Rendering 과정이라고도 합니다.

편의상 우리는 배치라고 할 겁니다.

기본 엘리먼트는 위에서 아래로 배치되는 것이 기본입니다.

하지만 웹사이트의 배치는 다양하게 표현 가능해야 하므로, 이를 다양한 방식으로 배치할 수 있도록 다양한 속성을 활용합니다.

중요하게 이해해야 할 속성은 다음과 같습니다.

* **display**(block, inline, inline-block)
* **position**(static, absolute, relative, fixed)
* **float**(left, right)

이 속성들을 잘 이해하는 것이 중요하다.



#### Display

**엘리먼트가 배치되는 방식 - (display:block)**

display속성이 **block**이거나 **inline-block**인 경우 그 엘리먼트는 벽돌을 쌓든 블록을 가지고 쌓입니다.

Ex) div, p

```html
<div>block1</div>
<p>block2</p>
<div>block3</div>
```


**엘리먼트가 배치되는 방식 - (display:inline)**

display 속성이 **inline**인 경우는 우측으로, 그리고 아래쪽으로 빈자리를 차지하며 흐릅니다.

높이와 넓이를 지정해도 반영이 되지 않습니다.

Ex) span, a, strong

```html
<div>
  <span>나는 어떻게 배치되나요?</span>
  <span>좌우로 배치되는군요</span>
  <a>링크는요?</a>
  <strong>링크도 강조도 모두 좌우로 흐르는군요</strong>
  모두다 display속성이 inline인 엘리먼트이기 때문입니다.
</div>
```

[code 바로가기](http://jsbin.com/wacukuf/edit?html,output)



#### POSITION

**엘리먼트가 배치되는 방식 (position:static, relative, absolute)**

엘리먼트 배치가 순서대로만 위아래로 또는 좌우로 흐르면서 쌓이기만 하면, 다양한 배치를 하기 어렵습니다.

position 속성을 사용하면 상대적/절대적으로 어떤 위치에 엘리먼트를 배치하는 것이 수월합니다. 

**1. position 속성으로 특별한 배치를 할 수 있습니다.**

position 속성은 기본 static입니다.
ㄴ그냥 순서대로 배치됩니다. 

**2. absolute는 기준점에 따라서 특별한 위치에 위치합니다.**

top / left / right / bottom 으로 설정합니다.

기준점을 상위엘리먼트로 단계적으로 찾아가는데 static이 아닌 position이 기준점입니다. **상위 엘리멘트 중에서 static이 아닌 애가 기준**

**3. relative는 원래 자신이 위치해야 할 곳을 기준으로 이동합니다.**

top / left / right / bottom로 설정합니다. 

**4 fixed는 viewport(전체화면) 좌측, 맨 위를 기준으로 동작합니다.**

[code 바로가기](http://jsbin.com/vegowut/edit?html,css,output)



**엘리먼트가 배치되는 방식 (margin:10px)**

margin으로 배치가 달라질 수 있습니다.
margin은 위 / 아래 / 좌 / 우 엘리먼트와 본인 간의 간격입니다.
따라서 그 간격만큼 내 위치가 달라집니다.



#### Float

**엘리먼트가 배치되는 방식 (float:left)**

float 속성으로 원래 flow에서 벗어날 수 있고 둥둥 떠다닐 수 있습니다.

일반적인 배치에 따라서 배치된 상태에서 float는 벗어난 형태로 특별히 배치됩니다.

따라서 뒤에 block엘리먼트가 float 된 엘리먼트를 의식하지 못하고 중첩돼서 배치됩니다.

[code 바로가기](http://jsbin.com/cutivij/2/edit?html,css,output)

float의 속성은 이런 특이성 때문에 웹사이트의 전체 레이아웃 배치에서 유용하게 활용됩니다.


**엘리먼트가 배치되는 방식 (box-model)**

블록 엘리먼트의 경우 box의 크기와 간격에 관한 속성으로 배치를 추가 결정합니다.
**margin, padding, border, outline**으로 생성되는 것입니다.

[code 바로가기](https://www.w3schools.com/css/css_boxmodel.asp)

box-shadow 속성도 box-model에 포함지어 설명할 수 있습니다.
box-shadow는 border 밖에 테두리를 그릴 수 있는 속성입니다.

단축 표기법 : 위 우 아래 좌 순서(4) / 위아래 좌우(2) 


**엘리먼트의 크기**

block엘리먼트의 크기는 기본적으로는 부모의 크기만큼을 가집니다.

예를 들어, width:100%는 부모의 크기만큼을 다 갖는 것과 같습니다.


**box-sizing과 padding**

padding 속성을 늘리면 엘리먼트의 크기가 달라질 수 있습니다.

box-sizing 속성으로 이를 컨트롤 할 수 있습니다.

box-sizing 속성을 border-box로 설정하면 엘리먼트의 크기를 고정하면서 padding 값만 늘릴 수 있습니다.

[code 바로가기](http://jsbin.com/wosuwop/edit?html,css,output)



##### layout 구현방법은?

* 전체 레이아웃은 **float**를 잘 사용해서 2단, 3단 컬럼 배치를 구현합니다.최근에는 **css-grid나 flex 속성** 등 layout을 위한 속성을 사용하기 시작했으며 브라우저 지원범위를 확인해서 사용하도록 합니다.

* **특별한 위치에 배치**하기 위해서는 **position absolute**를 사용하고, **기준점을 relative**로 설정합니다.

* 네비게이션과 같은 엘리먼트는 block 엘리먼트를 inline-block으로 변경해서 가로로 배치하기도 합니다.

* 엘리먼트안의 텍스트의 간격과 다른 엘리먼트간의 간격은 padding과 margin 속성을 잘 활용해서 위치시킵니다.



### float 기반 샘플 화면 레이아웃 구성

float는 자식값으로 생각안함. 그래서 overflow를 써서 한다.

**기본배치를 한 이후에 필요한 부분을 float를 사용해서 좌/우로 배치하는 것이 일반적입니다.**

**비율조정은 %를 사용**해서 배치할 수도 있습니다.

레이아웃을 배치하는데 **flex**라는 속성도 있습니다. flex 속성은 많은 기능을 제공하지만, 간단히 좌/우로 배치하는 방식이 어떻게 구현하는지 찾아봅니다.

* flex 속성은 많은 기능을 제공하는데 좌/우 배치는 어떻게 하나요?

  clear(left, right, both) 속성을 통해 float인 엘리먼트들을 인식하게 할 수 있다.

* float와의 차이점을 느껴보세요.

  부모는 float자식을 인식하지 못함(속성이 삭송되지 않음). overflow 속성을 통해 float자식을 인식할 수 있다.

[명훈 코드](https://codepen.io/azderica/pen/YzyVWYN)

### 디버깅-HTML-CSS

크롬 개발자도구의 Element panel을 잘 익혀두는 것이 중요합니다.

개발자도구를 통해서 쉽게 할 수 있는 일들을 정리하면 다음과 같습니다.

- CSS Style을 inline 방식으로 빠르게 테스트할 수 있습니다.
- 현재 엘리먼트의 값을 임시로 바꿀 수 있습니다.
- 최종 결정된 CSS 값을 확인할 수 있습니다.

맥북은 `option + command + I` 를 잘쓰는 게 중요.