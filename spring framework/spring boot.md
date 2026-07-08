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

