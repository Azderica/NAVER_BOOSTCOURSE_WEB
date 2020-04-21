## 네이버 부스트 코스 1주차

### Web개발의 이해

#### 웹 관련 인기 언어

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

