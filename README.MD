Приложение создано по видео (letsCode):

1) https://www.youtube.com/watch?v=jH17YkBTpI4

http://localhost:8080/greeting
http://localhost:8080/greeting?name=User
http://localhost:8080


    https://spring.io/guides/gs/serving-web-content/

    This controller is concise and simple, but there is plenty going on. We break it down step by step.
    The @GetMapping annotation ensures that HTTP GET requests to /greeting are mapped to the greeting() method.
    @RequestParam binds the value of the query string parameter name into the name parameter of the greeting() method. This query string parameter is not required. If it is absent in the request, the defaultValue of World is used. The value of the name parameter is added to a Model object, ultimately making it accessible to the view template.
    The implementation of the method body relies on a view technology (in this case, Thymeleaf) to perform server-side rendering of the HTML. Thymeleaf parses the greeting.html template and evaluates the th:text expression to render the value of the ${name} parameter that was set in the controller.

    @SpringBootApplication is a convenience annotation that adds all of the following:
    @Configuration: Tags the class as a source of bean definitions for the application context.
    @EnableAutoConfiguration: Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings. For example, if spring-webmvc is on the classpath, this annotation flags the application as a web application and activates key behaviors, such as setting up a DispatcherServlet.
    @ComponentScan: Tells Spring to look for other components, configurations, and services in the com/example package, letting it find the controllers.


Дополнение:

    В качестве обучения добавления новых зависимостей, мы заменяем шаблонизатор по умолчанию Thymeleaf на более простой - Mustache. Ссылка на зависимости:
    <dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-mustache</artifactId>
    </dependency>
    Ссылка на руководство по Mustache:
    http://mustache.github.io/mustache.5.html