# 네이버 부스트 코스 1주차

## [FE/BE]

#### Web개발의 이해 [LINK](./1-Web-Intro/README.md)

1. 웹 프로그래밍을 위한 프로그램 언어들
2. 웹의 동작(HTTP 프로토콜 이해)
3. 웹 Front-End 와 웹 Back-End
4. Browser의 동작
5. Browser에서의 웹 개발
6. 웹서버
7. WAS

## [:sunny:FE]

#### HTML [LINK](./2-HTML/README.md)

1. HTML Tags
2. HTML Layout 태그
3. HTML 구조설계
4. class와 id 설계

#### CSS [LINK](./3-CSS/README.md)

1. CSS 선언방법
2. 상속과 우선순위 결정
3. CSS Selector
4. CSS 기본 Style 변경하기
5. Element가 배치되는 방법(CSS layout)
6. float 기반 샘플 화면 레이아웃 구성
7. 디버깅 - HTML - CSS

## [:cloud:BE]

#### 개발환경 설정 [LINK](./4-Develop-Environment/README.md)

1. JDK 다운받기 및 설치하기
2. 환경설정하기
3. 이클립스 다운받기 및 설치하고 인코딩 설정하기
4. HelloWorld 컴파일하고 실행하기
5. Tomcat 다운받기 및 설치하기
6. HelloWorld 서블릿 컴파일 및 실행하기

#### Servlet [LINK](./5-Servlet/README.md)

1. Servlet이란?
2. Servlet 작성 방법
3. Servlet 라이프 싸이클
4. Request, Response 객체 이해하기

## [Summary]

#### 파트1. 웹 프로그래밍 기초 - 웹 프론트엔드

- 프론트엔드와 백엔드의 역할과 관계
- HTML로 웹페이지 구조 설계
- CSS 레이아웃에 필요한 속성과 활용방법

#### 파트1. 웹 프로그래밍 기초 - 웹 백엔드

- 웹 개발에 대한 이해
- 개발 환경 설정
- 서블릿(Servlet)

## [Project]

자기소개 페이지 만들기

> [관련 요구 사항](https://docs.google.com/presentation/d/1Q0qZO7mEh5VFcm2riFsP0XViNaKUP7Bj5NCjiia3hyo/edit)

**웹프론트엔드 기술요구사항**

- html layout tag를 사용합니다.
- classname은 일정한 컨벤션을 유지합니다.
- 의미에 맞는 tag를 최대한 사용합니다. (div 사용은 최대한 자제)
- position속성과 float를 사용해서 element를 배치합니다.
- 라이브러리를 사용한 레이아웃은 지양합니다. (부트스트랩 등)
- id와 class등의 다양한 selector문법을 잘 활용해야 합니다.

**웹백엔드 기술요구사항**

- 톰캣서버를 통해서 자기소개 페이지가 동작되야 합니다. (ex http://localhost:8080/aboutme/index.html 에서 노출)
- 서블릿페이지하나를 생성해서, url을 입력했을 때 시간데이터가 화면에 노출돼야 합니다.
