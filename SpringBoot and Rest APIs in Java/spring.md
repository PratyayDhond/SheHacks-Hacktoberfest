**What is SpringBoot?**

Spring Boot is an open source Java-based framework used to create a micro Service.

It is developed by Pivotal Team and is used to build stand-alone and production ready spring applications. This chapter will give you an introduction to Spring Boot and familiarizes you with its basic concepts.

Spring Boot enables developers to build applications that are ready to use right away. By embedding a web server like as Tomcat or Netty into your program during the initialization phase, you may create independent applications that function without the need for an external web server.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/1f3gn4t842x16i5kudu9.png)

**Reasons to Use Spring for making restful web services in Java**

1. Spring Integration's HTTP support allows for the running of HTTP requests and the processing of inbound HTTP requests. The HTTP support consists of the following gateway implementations: HttpInboundEndpoint and HttpRequestExecutingMessageHandler.

2. In the case of REST, the illustration of information is incredibly necessary, and that's why Spring MVC permits you to bypass View-based rendering altogether by victimization the @ResponseBody annotation and numerous HttpMessageConverter implementations.

3. Spring 4.0 unleashes more fervent annotation @RestController to create the event of restful web services even easier.
If you annotate your controller class using @RestController rather than @Controller then Spring applies message conversations to all or any handler strategies within the controller.

4. One of the most distinctions between REST web services and a standard web application is that REST passes resource symbol information in URI.

If you remember, we use @RequestParam to induce the worth of these query parameters however to not worry, Spring MVC additionally provides a @PathVariable annotation which might extract data from the URL. It permits the controller to handle requests for parameterized URLs.

5. Another key facet of restful web services is the illustration, for instance, a similar resource may be diagrammatic in numerous formats e.g. JSON, XML, HTML, and so on fortunately Spring provides several read implementations and views resolvers to render information as JSON, XML, and HTML.

6. Similar to @ResponseBody annotation, which is used for changing the response to the format consumer needs (by victimization HttpMessageConverts), Spring MVC additionally provides @RequestBody annotation, which uses HTtpMethodConverter implementations to convert incoming HTTP information into Java objects passed into a controller's handler method.

7. The Spring framework also provides a template class, RestTemplatewhich is similar to JdbcTemplate, and, JmsTemplate, can consume REST resources. You can use this class to test your RESTful web service or develop REST clients.
Restful web service in JAVA


REST has now become a standard way to develop web services, and there are many frameworks and libraries available for Java, such as Jersey, RESTEasy, JAX-RS, Restlet, Apache CFX, and others. Still, I recommend that Java developers use Spring Model-View-Controller to create RESTful web services.

Some may wonder why the Spring Model-View-Controller Framework is used to create RESTful web services in Java. What are the benefits, and why is it superior to other frameworks and libraries available?

The most important reason, in my opinion, to use Spring for developing RESTful web services is that you can use your Spring Model-View-Controller experience to develop RESTful web services without having to learn a new framework or library, allowing you to quickly roll out your REST API.

This is one of the most significant benefits, I mean leveraging your years of experience with Spring Model-View-Controller to expose your code.

Another reason is that Spring has wonderful support for developing restful web services. within the last number of versions, ranging from Spring version 3.0, It's provided a lot of enhancements to Spring MVC to supply fantabulous REST support. It's provided dedicated annotations, like @RestController and @ResponseStatus, to form the event of quiet resources even easier in Spring 4.0. It's additionally not solely helps you to form quiet web services however also provides categories to consume REST resources such as you will use the RestTemplate class to consume quiet resources. There are more utility classes and annotations that build the event of quiet net services in Spring easier and a lot of seamless, and I'll share a handful of them during this article to prove my purpose that victimization Spring to develop restful net service is that the right decision.


![Image description](https://dev-to-uploads.s3.amazonaws.com/uploads/articles/ekadbnktyg7enuub16md.png)

**Advantages and Disadvantages of SpringBoot**

**Advantages**

Simplified & version conflict free dependency management through the starter POMs.

We can quickly setup and run standalone, web applications and micro services at very less time.

You can just assemble the jar artifact which comes with an embedded Tomact, Jetty or Undertow application server and you are ready to go.

Spring Boot provides HTTP endpoints to access application internals like detailed metrics, application inner working, health status, etc.

No XML based configurations at all. Very much simplified properties. The beans are initialized, configured and wired automatically.

The Spring Initializer provides a project generator to make you productive with the certain technology stack from the beginning. You can create a skeleton project with web, data access (relational and NoSQL datastores), cloud, or messaging support.

**Disadvantages**

Spring boot may unnecessarily increase the deployment binary size with unused dependencies.

If you are a control freak, I doubt Spring Boot would fit your needs.

Spring Boot sticks good with micro services. The Spring Boot artifacts can be deployed directly into Docker containers. In a large and monolithic based applications, I would not encourage you to use Spring Boot.