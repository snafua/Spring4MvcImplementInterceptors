# Spring4MvcImplementInterceptors

* Spring 4 + MVC + Java Configuration + Maven + Interceptors, Example
* Template example for Spring 4 MVC + JSP View with pure Java Configuration (no XML), using Maven build tool.
* Spring4 + MVC, Integration without using the web.xml and Spring_Servlet.xml file. 
* By using WebMvcConfigurerAdapter class and WebApplicationInitializer interface to replace above files.
* By Implementing HandlerInterceptor interface or extending handlerinterceptoradapter class
* Ref: https://www.journaldev.com/2676/spring-mvc-interceptor-example-handlerinterceptor-handlerinterceptoradapter

> **###1. Technologies**
* Spring 4.0.6.RELEASE
* Maven 3.1
* JSTL 1.2

> **###2. To Run this project locally**
* $ git clone https://github.com/AkashChauhanSoftEngi/Spring4MvcImplementInterceptors
* $ mvn tomcat7:run

> **###3.  Access** 
* http://localhost:8080/Spring4MvcImplementInterceptors

> **###4. Addtional Information**
* To get rid of web.xml [Includes Dispature Servlet Information] you need to extend a class name WebApplicationInitializer
  and have to register configuration file, give details of mapping from where should servlet start reading content
```java
    public class HelloWorldInitializer implements WebApplicationInitializer {
    }
```
* To get rid of AppConfiguration.xml [Beans declaration] file, you need to extend WebMvcConfigurerAdapter class
  and have to add @Configuration, @EnableWebMvc and @ComponentScan(basePackages = "com.project") annotations
* Also have to override viewResolver() for accesing JSP files if any
* There are Other overriding methods as well in WebMvcConfigurerAdapter class
```java
    @Configuration
    @EnableWebMvc
    @ComponentScan(basePackages = "com.project")
    @PropertySource("classpath:messages.properties")
    public class HelloWorldConfiguration extends WebMvcConfigurerAdapter {
    }
```
