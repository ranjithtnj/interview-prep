# Now Spring Boot

## 1. What is Spring Boot?

Spring Boot is built on top of Spring.

Spring Boot makes Spring easier to use.

### Simple meaning:

Spring Boot helps us create Spring applications quickly with minimum configuration.


## 2. Why Spring Boot?

Spring is powerful, but earlier it needed a lot of setup.

### Before Spring Boot, we had to configure:

* XML files
* Tomcat server
* DispatcherServlet
* Dependency versions
* Database setup
* MVC configuration

Spring Boot reduces this manual setup.


### 1. XML files

#### What?

Earlier Spring projects used XML files to tell Spring:

* Which classes should be created as objects?

#### Example (Old-style XML)

```xml
<bean id="userService" class="com.example.UserService" />
<bean id="userRepository" class="com.example.UserRepository" />
```

**This means:**

> Spring, please create objects for UserService and UserRepository.

#### Why was it difficult?

For many classes, XML becomes large and hard to maintain.

#### How Spring Boot helps?

Now we use annotations.

```java
@Service
public class UserService {
}
```

Spring Boot scans and creates the object automatically.

### 2. Tomcat Server

#### What?

Tomcat is a server used to run Java web applications.

Without server, your API cannot receive requests.

#### Example

```text
Browser → Tomcat → Spring Application
```

#### Before Spring Boot

You had to:

* Install Tomcat separately
* Build WAR file
* Deploy WAR into Tomcat

#### With Spring Boot

Tomcat comes inside the application.

You just run:

```bash
java -jar app.jar
```

Spring Boot starts Tomcat automatically.

### 3. DispatcherServlet

#### What?

DispatcherServlet is the main entry point for Spring MVC.

It receives HTTP requests and sends them to the correct controller.

#### Example

```text
GET /users
   ↓
DispatcherServlet
   ↓
UserController
```

#### Before Spring Boot

You had to configure DispatcherServlet manually.

#### With Spring Boot

Spring Boot automatically creates and registers DispatcherServlet when you add:

```text
spring-boot-starter-web
```

Then this works directly:

```java
@RestController
public class UserController {

    @GetMapping("/users")
    public String getUsers() {
        return "User list";
    }
}
```
### 4. Dependency Versions

#### What?

Dependencies are external libraries used in your project.

#### Example

* spring-core
* spring-web
* jackson
* tomcat
* hibernate
* mysql-driver

#### Before Spring Boot

You had to choose correct versions manually.

#### Problem

* spring-web version 5
* jackson version 2
* tomcat version 8

Sometimes versions did not match and caused errors.

#### With Spring Boot

Spring Boot manages compatible versions for you.

#### Example

```xml
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

This single starter brings compatible versions of:

* Spring MVC
* Jackson
* Tomcat
* Validation support

### 5. Database Setup

#### What?

For database, we need:

* Database URL
* Username
* Password
* Driver
* Connection pool
* Transaction manager
* JPA/Hibernate configuration

#### Before Spring Boot

You had to configure many beans manually.

#### Example

* DataSource
* EntityManagerFactory
* TransactionManager

#### With Spring Boot

You mostly add properties:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/testdb
spring.datasource.username=root
spring.datasource.password=password
spring.jpa.hibernate.ddl-auto=update
```

And dependency:

```text
spring-boot-starter-data-jpa
```

Spring Boot automatically configures:

* DataSource
* Hibernate
* EntityManager
* TransactionManager

### 6. MVC Configuration

#### What?

MVC means:

* Model
* View
* Controller

For REST APIs, Controller handles request and response.

#### Before Spring Boot

You had to manually configure:

* Component scanning
* JSON converter
* Request mapping
* View resolver
* Static resources

#### With Spring Boot

Add:

```text id="dxm41y"
spring-boot-starter-web
```

Then directly write:

```java id="h5p4qg"
@RestController
public class ProductController {

    @GetMapping("/products")
    public List<String> getProducts() {
        return List.of("Laptop", "Mobile");
    }
}
```

Spring Boot automatically converts Java object to JSON:

```json id="5lbo7j"
["Laptop", "Mobile"]
```

---

## Simple Final Comparison

### Before Spring Boot

Developer had to say:

* Create these objects
* Configure Tomcat
* Configure DispatcherServlet
* Manage library versions
* Configure database
* Configure MVC

### With Spring Boot

Developer mainly says:

* I want to build a web app
* I want to connect database

Spring Boot does most setup automatically.

---

## Very Simple Summary

Spring Boot helps because:

* Less configuration
* Less boilerplate
* Faster development
* Easy to run
* Production-ready features

Spring Boot does not replace Spring.

It makes Spring easier.

