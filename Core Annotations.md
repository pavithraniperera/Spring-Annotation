## 1.  @Configuration

 
✖️`@Configuration` marks a class as a source of bean definitions. It is typically used in classes that define Spring beans.

✖️The `@Configuration` annotation is used to define beans and configuration settings for your Spring application.


**Sample Code:**
```java
@Configuration
public class AppConfig {
    @Bean
    public MyService myService() {
        return new MyServiceImpl();
    }
}
```
## 2.  @Component
✖️ `@Component` marks a class as a Spring-managed component, making it eligible for auto-detection when using annotation-based configuration and classpath scanning.

✖️ This annotation is used when you want Spring to manage your class as a bean automatically, and you want to avoid explicitly defining it in the configuration file.

```java
@Component
public class MyComponent {
    public void doSomething() {
        System.out.println("Doing something...");
    }
}

}
```
## 3. @Bean
✖️ @Bean is used to declare a Spring bean in a configuration class.
```java
@Configuration
public class AppConfig {

    @Bean
    public MyService myService() {
        return new MyServiceImpl();
    }
}

```
## 4. @Autowired

✖️ @Autowired allows Spring to resolve and inject dependencies automatically by type.

✖️ Use this annotation to inject the dependencies that your component needs, reducing boilerplate code for setting up dependencies manually.

```java
@Component
public class MyService {

    @Autowired
    private MyRepository repository;

    public void performTask() {
        repository.save(new MyEntity());
    }
}
```
## 5.  @Primary
  
✖️ `@Primary` is used to indicate a preference for a specific bean when multiple beans of the same type are available for autowiring.
Use @Primary when you want to mark one bean as the default choice, so Spring knows which one to inject in case of ambiguity.

 If no specific @Qualifier is provided, the @Primary bean will be injected by default.

## 6.  @Qualifier


✖️ `@Qualifier` specifies which bean to inject when multiple candidates of the same type exist.


```java
@Component
public class MyService {

    @Autowired
    @Qualifier("specialRepository")
    private MyRepository repository;

    public void performTask() {
        repository.save(new MyEntity());
    }
}
```
## 7.  Scope Annotations

@scope  Specifies the scope of a bean (e.g., `singleton`, `prototype`, etc.).
  
```java
@Component
@Scope("prototype")
public class MyPrototypeBean {
    // Bean definition
}
```
@RequestScope: Specifies that a bean should be scoped to an HTTP request.

@SessionScope: Specifies that a bean should be scoped to an HTTP session.

## 7.  Life cycle Annotations

###  @PostConstruct

✖️ Marks a method to be invoked after a bean's initialization (called after dependency injection).

```java
@Component
public class MyBean {

    @PostConstruct
    public void init() {
        // Initialization code
    }
}
```
### @PreDestroy

✖️ Marks a method to be invoked before a bean is removed from the container (just before it is destroyed).

```java
@Component
public class MyBean {

    @PreDestroy
    public void cleanup() {
        // Cleanup code
    }
}
```


