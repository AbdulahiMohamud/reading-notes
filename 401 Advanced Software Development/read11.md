## Spring MVC and Thymeleaf

### How to access data from templates

-In a typical Spring MVC application, **@Controller** classes are responsible for preparing a model map with data and selecting a view to be rendered
-Thymeleaf, it is transformed into a Thymeleaf context object (part of the Thymeleaf template execution context) that makes all the defined variables available to expressions executed in templates.
-Spring MVC calls the pieces of data that can be accessed during the execution of views model attributes.The equivalent term in Thymeleaf language is context variables.

## Spring model attributes

### Adding model attributes to a view in Spring MVC

-Add attribute to Model via its addAttribute method:
-Add attribute to Model via its addAttribute method:
-Expose common attributes via methods annotated with @ModelAttribute:

#### You can access model attributes in views with Thymeleaf as follows

`<tr th:each="message : ${messages}">
          <td th:text="${message.id}">1</td>
          <td><a href="#" th:text="${message.title}">Title ...</a></td>
             <td th:text="${message.text}">Text ...</td>
      </tr>`

## Request Parameters

-Request parameters can be easily accessed in Thymeleaf views. Request parameters are passed from the client to server like:
> <https://example.com/query?q=Thymeleaf+Is+Great>!

-In order to access the q parameter you can use the param. prefix:
>     <p th:text="${param.q}">Test</p>
In the above example if parameter q is not present, empty string will be displayed in the above paragraph otherwise the value of q will be shown.
-Parameters can be multivalued e.g
> <https://example.com/query?q=Thymeleaf%20Is%20Great!&q=Really%3F>

- You can access them using

`<p th:text="${param.q[0] + ' ' + param.q[1]}" th:unless="${param.q == null}">Test</p>`

- Another way to access request parameters is by using the special #request object that gives you direct access to the javax.servlet.http.HttpServletRequest object:

`<p th:text="${#request.getParameter('q')}" th:unless="${#request.getParameter('q') == null}">Test</p>`

## Session attributes

-Similarly to the request parameters, session attributes can be accessed by using the session. prefix:
`<p th:text="${session.mySessionAttribute}" th:unless="${session == null}">[...]</p>`

- You can also use #session

## SerletContext attribute

-The ServletContext attributes are shared between requests and sessions.
-In order to access ServletContext attributes in Thymeleaf you can use the #servletContext.

## Spring Bean

-Thymeleaf allows accessing beans registered at the Spring Application Context with the @beanName syntax, for example;
`<div th:text="${@urlService.getApplicationUrl()}">...</div>`

## Reference and Citation

> Hambalieu Jallow