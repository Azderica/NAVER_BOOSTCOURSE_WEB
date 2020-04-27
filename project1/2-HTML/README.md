# 네이버 부스트 코스 1주차

## HTML

### HTML Tags

HTML의 태그는 그 의미에 맞쳐서 사용해야한다.

> 링크, 이미지, 목록, 제목 등등
>
> anchor, img, ul/li, heading, p, div 등이 주로 쓰인다.

```html
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
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

최신 브라우저가 많은 모바일 브라우저의 경우에는 footer을 써도 좋다.(데스크톱 환경에서는 글쎄) div랑 사실 똑같다.

```html
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
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
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>JS Bin</title>
  </head>
  <body>
    <header>
      <h1>Company Name</h1>
      <img src="..." alt="logo" />
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

- 고유한 속성으로 한 HTML 문서에 하나만 사용 가능
- 고유한 ID 값이 있으면 하나하나에 특별한 제어를 할 수 있으며 검색에도 용이

#### Class

- 하나의 HTML문서 안에 중복해서 사용 가능
- 하나의 태크에 여러 개의 다른 class 이름을 공백을 기준으로 나열 가능
- 홈페이지 전체적인 스타일을 일관성 있게 지정하기 위해는 class 사용이 필수적

이렇게 구분할 수 있지만, 회사마다 어떠한 약속(convention)을 만들어서 자신들만의 규칙을 사용.

> ex) ID사용을 금하거나 class로만 사용하는 경우가 존재

#### Q. Class name을 잘 설정하는 방법은?

**BEM**, 알아보기 쉬워야 유지보수가 쉬움

**BEM(Block Element Modifier)** 은 CSS Architecture의 하나.

1. **Block**(전체를 감싸고 있는 블럭 요소)

- 독립적으로 의미가 있는 컴포넌트를 의미

```html
<div class="block">...</div>
```

- Header, footer, nav, main 등의 컨텐츠 영역을 block으로 간주할 수 있음
- 더 구체적으로 본다면 header block은 logo block, search form block, authorization block을 포함할 수 있음

![Block 예시](https://junwoo45.github.io/img/css_architecture3.png)

- block은 클래스의 어근을 형성하고 항상 맨 앞에 위치한다

2. **Element**

- 독립적으로는 의미가 없으며 Block에 붙어서 사용되는 컴포넌트

```html
<div class="block">
  <span class="block__element">...</span>
</div>
```

- element는 block이 포함하고 있는 한 조각
- 예를 들어 위에서 보았던 block이미지에서, menu item은 menu block 바깥에서는 사용될 수 없다. 따라서 각각의 메뉴아이템은 element이다.

![Element 예시](https://junwoo45.github.io/img/css_architecture4.png)

- 두개의 **underscore로** 연결하여 블럭 다음에 위치 시킨다.

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

- modifier는 block또는 element의 속성

  이 속성은 block이나 element의 외관이나 상태를 변화

  기본적으로, class 명은 반복하여 재사용할 수 있게 하기 위해 존재

  특정 요소의 스타일을 수정해야할 필요가 있을때 modifier를 활용하게 된다.

  이때, element나 block다음에 두개의 하이픈 '--'을 추가하여 modifier를 표시한다.

```css
.block__element--modifier {
  display: none;
}
```

- 다음처럼 focuesed된 tab3를 modifiers라고 볼 수 있다.

![modifier 예시](https://junwoo45.github.io/img/css_architecture5.png)

- 다른 예시, 아래와 같은 버튼을 만드는 경우

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
  border: 1px solid #d5d5d5;
  background-image: linear-gradient(#eee, #ddd);
  font: 700 13px/18px Helvetica, arial;
}
.button--state-success {
  color: #fff;
  background: #569e3d linear-gradient(#79d858, #569e3d) repeat-x;
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
