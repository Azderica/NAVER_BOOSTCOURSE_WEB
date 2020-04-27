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
