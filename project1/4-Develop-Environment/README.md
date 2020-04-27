# 네이버 부스트 코스 1주차

## JDK 다운받기 및 설치하기

mac 설치 위치 : [자바 jdk 8 받기](https://www.oracle.com/java/technologies/jdk8-downloads.html)

## 환경설정하기

java path 설정

## 이클립스 + 설치 및 인코딩

mac 유저 이클립스 설치 : `brew cask install eclipse-jee;`

## 프로젝트 시작하기

Java Code Conventions (프로그래머들끼리의 약속)

- **클래스명** : 첫글자를 대문자로
- **프로젝트명, 패키지명** : 소문자

기억해두세요.

더 많은 Java Code Conventions은 참고 링크에 넣어 두었습니다.

최근에는 이클립스말고 VSCode나 Intellij를 쓴다.

이클립스는 코드 개발부터 빌드 테스트 디버깅 배포까지 다른 IDE들에 비해 해줘야할 것이 많음.

[자바 코딩 규칙](https://myeonguni.tistory.com/1596)

## Tomcat

### Apache Tomcat

[관련 영상 자료](https://www.youtube.com/watch?v=h_qQOVDTxo8&feature=youtu.be)

tomcat 켜기 : `./start.sh`

tomcat 끄기 : `./shutdown.sh`

**catalina**

`./catalina.sh start`

`./catalina.sh stop`

## Servlet

자바 이클립스에서 URL 주소를 만들어주는 규칙은 다음과 같다.

`http://localhost:8080/{프로젝트이름}/{URL Mapping값}`

아래는 해당 예시 코드이다.

```java
package examples;

import java.io.IOException;
import java.io.PrintWriter;

import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class HelloServlet
 */
@WebServlet("/HelloServlet")
public class HelloServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;

    /**
     * @see HttpServlet#HttpServlet()
     */
    public HelloServlet() {
        super();
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		// response.getWriter().append("Served at: ").append(request.getContextPath());
		response.setContentType("text/html;charset=UTF-8");
		PrintWriter out = response.getWriter();
		out.print("<h1>Hellow servlet</h1>");
	}

}

```
