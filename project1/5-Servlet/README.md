# 네이버 부스트 코스 1주차

## Servlet이란?

### 자바 웹 어플리케이션(Java Web Application)

* WAS에 설치(deploy)되어 동작하는 어플리케이션
* 자바 웹 어플리케이션에는 HTML, CSS, 이미지, 자바로 작성된 클래스(Servlet도 포함됨, package, 인터페이스 등), 각종 설정 파일 등이 포함

### 자바 웹 어플리케이션의 폴더 구조

![img](https://cphinf.pstatic.net/mooc/20180124_133/15167752967943AqfC_PNG/1_5_1_____.PNG)

> 자바 웹 어플리케이션의 폴더 구조

이 폴더 구조를 지켜줘야한다. - web. 폴더가 꼭 필요하다.

#### 이클립스에서 실행된 Dynamic Web Project

![image](https://user-images.githubusercontent.com/42582516/80353260-123f9580-88b0-11ea-83f3-a0bffd8b25df.png)

> firstWeb의 폴더 구조

이클립스에서 Dyanmic Web Project의 Servlet을 실행하면, 해당 프로젝트가 이클립스가 관리하는 .metadata 폴더아래에 자바 웹 어플리케이션 폴더 구조로 만들어져 실행함

### 서블릿이란?

* 자바 웹 어플리케이션의 구성요소 중 동적인 처리를 하는 프로그램의 역할입니다.
* 서블릿을 정의해보면 
  * **서블릿(servlet)**은 **WAS에 동작하는 JAVA 클래스**입니다. 
  * **서블릿**은 **HttpServlet 클래스를 상속**받아야 합니다.
  * 서블릿과 JSP로부터 최상의 결과를 얻으려면, 웹 페이지를 개발할 때 이 두 가지**(JSP, 서블릿)를 조화롭게 사용**해야 합니다.
  * 예를 들어, 웹 페이지를 구성하는 **화면(HTML)은 JSP로 표현**하고, **복잡한 프로그래밍은 서블릿**으로 구현합니다.



## Servlet 작성 방법

### 버전에 따른 Servlet 작성 방법

**1. Servlet 3.0 spec 이상에서 사용하는 방법**

- web.xml 파일을 사용하지 않습니다.

- 자바 **어노테이션(annotation)**을 사용합니다.

- 앞에서 실습했던 first web에서 사용합니다.

  - ```java
    @WebServlet("/ten")
    public class TenServlet extends HttpServlet
    ```

**2. Servlet 3.0 spec미만에서 사용하는 방법**

- servlet을 등록할 때 web.xml 파일에 등록합니다.



```java
@WebServlet("/ten")
public class TenServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    /**
     * @see HttpServlet#HttpServlet()
     */
    public TenServlet() {
        super();
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		response.setContentType("text/html;charset=utf-8");
		PrintWriter out = response.getWriter();
		out.println("<h1>1~10까지 출력!!<h1>");
		for(int i=1; i<=10; i++) {
			out.print(i + "<br>");
		}
		out.close();
	}

}
```

> 예시 코드 1

```xml
<?xml version="1.0" encoding="UTF-8"?>
<?xml version="1.0" encoding="UTF-8"?>
<web-app xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" 
xmlns="http://java.sun.com/xml/ns/javaee" 
xsi:schemaLocation="http://java.sun.com/xml/ns/javaee http://java.sun.com/xml/ns/javaee/web-app_2_5.xsd" 
version="2.5">
    <display-name>exam25</display-name>
    <welcome-file-list>
        <welcome-file>index.html</welcome-file>
        <welcome-file>index.htm</welcome-file>
        <welcome-file>index.jsp</welcome-file>
        <welcome-file>default.html</welcome-file>
        <welcome-file>default.htm</welcome-file>
        <welcome-file>default.jsp</welcome-file>
    </welcome-file-list>
    <servlet>
        <description></description>
        <display-name>TenServlet</display-name>
        <servlet-name>TenServlet</servlet-name>
        <servlet-class>exam.TenServlet</servlet-class>
    </servlet>
    <servlet-mapping>
        <servlet-name>TenServlet</servlet-name>
        <url-pattern>/ttt</url-pattern>
    </servlet-mapping>
</web-app>
```

> 예제 코드 2. xml을 통해 연결시켜야한다. Servlet 3.0이전 버전의 경우



#### Q. HttpServlet을 상속하지 않다는 이유?

상속받지않는다면 HttpServlet이 제공하는 메소드를 사용하지 못해 할 것입니다.

서블릿3.0이하버전에서 무조건 web.xml에 작성.

url이 /ten이라고 요청이들어오면 url - mapping에서 찾고, 못찾으면 404페이지나옴. 존재하면 servlet-name을 확인하고, servlet태그안에서 같은이름의 servlet-name이 잇는지 확인. url-pattern을 변경하면 요청하는 url이름이 바뀌는데 이때 반드시 서버를 다시 실행(restart)해야된다.
그걸 찾아서 실제로 찾아야할 servlet-class를 찾는다.



## Servlet 라이프 싸이클

### LifecycleServlet

HttpServlet의 3가지 메소드를 오버라이딩

- init()
- service(request, response)
- destroy()

서블릿 객체는 매번 객체를 만드는게 아니라, 있는 서비스의 경우에는 객체를 만들필요없이 service만 한다.

![Servlet](https://cphinf.pstatic.net/mooc/20180124_22/1516782982944xjogH_PNG/1_5_3_ServletLifcycle.PNG)

> Servlet

#### Servlet 생명주기

- WAS는 서블릿 요청을 받으면 해당 서블릿이 메모리에 있는지 확인합니다.
-  if (메모리에 없음) {
   \- 해당 서블릿 클래스를 메모리에 올림
   \- init() 메소드를 실행
  }
   \- service()메소드를 실행
- was가 종료되거나, 웹 어플리케이션이 새롭게 갱신될 경우 destroy() 메소드가 실행됩니다.

#### service(request, response) 메소드

HttpServlet의 service메소드는 템플릿 메소드 패턴으로 구현합니다.

- 클라이언트의 요청이 GET일 경우에는 자신이 가지고 있는 doGet(request, response)메소드를 호출
- 클라이언트의 요청이 Post일 경우에는 자신이 가지고 있는 doPost(request, response)를 호출

 #### LifecycleServlet 수정 실습

- Service(request, response)메소드 주석처리
- HttpServlet의 doGet(request, response)메소드 오버라이딩
- HttpServlet의 doPost(request, response)메소드 오버라이딩

## Request, Response 객체 이해하기

#### 요청과 응답

**WAS는 웹 브라우저로부터 Servlet요청을 받으면,**

- 요청할 때 가지고 있는 정보를 HttpServletRequest객체를 생성하여 저장합니다.
- 웹 브라우저에게 응답을 보낼 때 사용하기 위하여 HttpServletResponse객체를 생성합니다.
- 생성된 HttpServletRequest, HttpServletResponse 객체를 서블릿에게 전달합니다.

 ![img](https://cphinf.pstatic.net/mooc/20180124_79/15167843899250uB2H_PNG/1_5_4_request_response.PNG)



#### HttpServletRequest

- http프로토콜의 request정보를 서블릿에게 전달하기 위한 목적으로 사용합니다.
- 헤더정보, 파라미터, 쿠키, URI, URL 등의 정보를 읽어 들이는 메소드를 가지고 있습니다.
- Body의 Stream을 읽어 들이는 메소드를 가지고 있습니다.



#### HttpServletResponse

- WAS는 어떤 클라이언트가 요청을 보냈는지 알고 있고, 해당 클라이언트에게 응답을 보내기 위한 HttpServleResponse객체를 생성하여 서블릿에게 전달합니다.
- 서블릿은 해당 객체를 이용하여 content type, 응답코드, 응답 메시지등을 전송합니다.



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
 * Servlet implementation class ParameterServlet
 */
@WebServlet("/param")
public class ParameterServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    /**
     * @see HttpServlet#HttpServlet()
     */
    public ParameterServlet() {
        super();
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		response.setContentType("text/html");
		PrintWriter out = response.getWriter();
		out.println("<html>");
		out.println("<head><title>form</title></head>");
		out.println("<body>");

		String name = request.getParameter("name");
		String age = request.getParameter("age");
		
		out.println("name : " + name + "<br>");
		out.println("age : " +age + "<br>");
		
		out.println("</body>");
		out.println("</html>");
	}

}
```

> 예시 코드 1

![image](https://user-images.githubusercontent.com/42582516/80487003-109ccd00-8997-11ea-8c76-636277dd4440.png)

> 실행 화면 1

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
 * Servlet implementation class InfoServlet
 */
@WebServlet("/info")
public class InfoServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    /**
     * @see HttpServlet#HttpServlet()
     */
    public InfoServlet() {
        super();
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		response.setContentType("text/html");
		PrintWriter out = response.getWriter();
		out.println("<html>");
		out.println("<head><title>info</title></head>");
		out.println("<body>");

		String uri = request.getRequestURI();
		StringBuffer url = request.getRequestURL();
		String contentPath = request.getContextPath();
		String remoteAddr = request.getRemoteAddr();
		
		
		out.println("uri : " + uri + "<br>");
		out.println("url : " + url + "<br>");
		out.println("contentPath : " + contentPath + "<br>");
		out.println("remoteAddr : " + remoteAddr + "<br>");
		
		out.println("</body>");
		out.println("</html>");
	}
}

```

> 예시 코드 2

![image](https://user-images.githubusercontent.com/42582516/80487196-62455780-8997-11ea-87bf-147207b54056.png)

> 실행 화면 2