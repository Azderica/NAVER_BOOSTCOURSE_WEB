# 네이버 부스트 코스 1주차

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

