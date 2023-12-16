# Enterprise module (Java branch)

### Java Enterprise and Spring

#### What are the possible uses of reflection?

Reflection in Java is a powerful feature that allows you to inspect and manipulate classes, interfaces, fields, and methods at runtime. Here are some possible uses of reflection:

1. **Inspection of Classes:** Reflection can be used to get the class object of an unknown object. This is particularly useful in scenarios where you don't know the type of the object beforehand. For example, in a plugin-based architecture where you load classes at runtime, reflection allows you to inspect the class's methods, fields, constructors, and annotations.
2. **Dynamic Method Invocation:** It allows for the invocation of methods at runtime without knowing the method at compile time. This is useful in frameworks like Spring or applications that need to call user-defined scripts or modules.
3. **Manipulation of Properties and Methods:** Reflection allows you to access and modify private fields and methods of a class, which is generally not accessible due to encapsulation. This feature is used in frameworks for dependency injection, serialization/deserialization, and testing where access to non-public members is necessary.
4. **Creating Instances Dynamically:** Through reflection, you can instantiate classes dynamically using their names. This is useful in factory patterns or IoC (Inversion of Control) containers where objects are created and managed dynamically based on configuration or runtime requirements.
5. **Array Manipulation:** Reflection provides methods to dynamically create and manipulate arrays. This can be useful in generic libraries where you deal with array types not known at compile time.
6. **Annotation Processing:** Reflection is crucial for reading annotations at runtime. This is widely used in frameworks that leverage custom annotations for various purposes like mapping objects to database tables or handling HTTP requests in web applications.

#### What is Spring?
#### What is Spring Boot?
#### What is the major difference between the Standard edition (JSE) and Enterprise edition (JEE)? You can choose Spring (Spring Boot) instead of JavaEE. Focus on comparing them.
#### What are the advantages of the Spring Framework? Focus on the Core part.
#### What is a servlet? What is the purpose of DispatcherServlet in Spring?
#### When do you use RestControllers, when just simple Controllers?
#### What is Spring Application Context?
#### What are the main ways to define a bean in the Application Context?
#### Difference between .jar and .war files.
#### What are the major differences between Maven, Ant and Gradle?
#### What is Maven used for?
#### What does a pom.xml file contains in Maven?

### Object Relational Mapping, JPA

#### What is an ORM? What are the benefits, when to use?
#### What is the difference between JDBC and JPA? Which are the advantages and disadvantages of each? Give a general overview.
#### What is Hibernate? What are the advantages, limitations?
#### Name 3 different annotations used in JPA, what can they do for you?
#### What is object-relational impedance mismatch?
#### What is a JpaRepository? What are the 2 main methods to define queries in them?
#### Why is the Set preferred over List when we want to store OneToMany relations?
#### What kind of inheritance strategies are available? Which annotations are used to solve this?


#### Annotations
* Controller vs RestController:

  The RestController provides JSON responses, while the Controller responds using the name of a View. This View is responsible for rendering the HTML content with Thymeleaf.

* SpringBootApplication:

  This annotation marks your configuration class and triggers the auto-configuration and the component scanning as well.
