# MVC

Spring MVC란 Front Controller Pattern에 기초한 웹 MVC 프레임워크이다

- Spring MVC의 구성 요소
    - DispatcherServlet : front controller에 해당한다. 클라이언트의 모든 request를 접수만 하는 곳이다. spring-webmvc에 이미 잘 포함되어 있기 때문에 수정할 필요는 없으나 동작을 이해하는 것이 좋다. DispatcherServlet은 클라이언트의 모든 요청을 받아들여서 그 일에 대한 처리를 Infrastructure Component에게 보낸다.
    - Infrastructure Component : DispatcherServlet으로부터 요청을 위임 받는 곳을 의미하는데 HandlerMapping, HandlerAdapter, ViewResolver 이렇게 3가지가 있다.
        - HadlerMapping: 사용자의 request를 처리할 Controller가 누구인지를 DispatcherServlet에게 알려준다.
        - HandlerAdapter: 사용자의 request를 처리해줄 Controller를 호출하고 결과를 받아온다.
        - ViewResolver: 사용자의 요청에 적합한 View를 반환해서 결과를 보여줄 수 있게 한다.

- Spring MVC의 동작 원리



1. DispatcherServlet이 브라우저로부터 요청을 받는다.
2. DispatcherServlet은 요청된 URL을 HandlerMapping 객체에 넘기고, 호출해야 할 Controller 메소드(핸들러) 정보를 얻는다.
3.  DispatcherServlet이 HandlerAdapter 객체를 가져온다.
4. HandlerAdapter 객체의 메소드를 실행한다.
5. Controller 객체는 비즈니스 로직을 처리하고, 그 결과를 바탕으로 뷰(ex. JSP)에 전달할 객체를 Model 객체에 저장한다. DispatcherServlet에게 view name을 리턴한다.
6. DispatcherServlet은 view name을 View Resolver에게 전달하여 View 객체를 얻는다.
7. DispatcherServlet은 View 객체에 화면 표시를 의뢰한다.
8. View 객체는 해당하는 뷰(ex. JSP, Thymeleaf)를 호출하며, 뷰는 Model 객체에서 화면 표시에 필요한 객체를 가져와 화면 표시를 처리한다.