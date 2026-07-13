
week 3 
**Exercise 1: Configuring a Basic Spring Application**

**Scenario:**

Your company is developing a web application for managing a library. You need to use the Spring Framework to handle the backend operations.

**Steps:**

1. **Set Up a Spring Project:**
    
    - Create a Maven project named **LibraryManagement**.
        
    - Add Spring Core dependencies in the **pom.xml** file.
        
2. **Configure the Application Context:**
    
    - Create an XML configuration file named **applicationContext.xml** in the **src/main/resources** directory.
        
    - Define beans for **BookService** and **BookRepository** in the XML file.
        
3. **Define Service and Repository Classes:**
    
    - Create a package **com.library.service** and add a class **BookService**.
        
    - Create a package **com.library.repository** and add a class **BookRepository**.
        
4. **Run the Application:**
    
    - Create a main class to load the Spring context and test the configuration.
        

**Exercise 2: Implementing Dependency Injection**

**Scenario:**

In the library management application, you need to manage the dependencies between the BookService and BookRepository classes using Spring's IoC and DI.

**Steps:**

1. **Modify the XML Configuration:**
    
    - Update **applicationContext.xml** to wire **BookRepository** into **BookService**.
        
2. **Update the BookService Class:**
    
    - Ensure that **BookService** class has a setter method for **BookRepository**.
        
3. **Test the Configuration:**[your](https://docs.google.com/forms/u/1/d/e/1FAIpQLSdKiBH5hbB17mJ2svIlMReBc_mfs7gIkLc9gQG_KF5KJWhRNQ/viewform?usp=already_responded&edit2=2_ABaOnudAd2YLiI4lPRVNkfMgSISlR41R2rtGLdtOhhU7OhHFlcBaylEDQ4ZsWdvpfA)
    
    - [your](https://docs.google.com/forms/u/1/d/e/1FAIpQLSdKiBH5hbB17mJ2svIlMReBc_mfs7gIkLc9gQG_KF5KJWhRNQ/viewform?usp=already_responded&edit2=2_ABaOnudAd2YLiI4lPRVNkfMgSISlR41R2rtGLdtOhhU7OhHFlcBaylEDQ4ZsWdvpfA)Run the **LibraryManagementApplication** main class to verify the dependency injection.
        

  
  

  
  

  
  

**Exercise 4: Creating and Configuring a Maven Project**

**Scenario:**

You need to set up a new Maven project for the library management application and add Spring dependencies.

**Steps:**

1. **Create a New Maven Project:**
    
    - Create a new Maven project named **LibraryManagement**.
        
2. **Add Spring Dependencies in pom.xml:**
    
    - Include dependencies for Spring Context, Spring AOP, and Spring WebMVC.
        
3. **Configure Maven Plugins:**
    
    - Configure the Maven Compiler Plugin for Java version 1.8 in the pom.xml file.

**Hands on 1**

**Spring Data JPA - Quick Example**   
  
**Software Pre-requisites**

- MySQL Server 8.0
    
- MySQL Workbench 8
    
- Eclipse IDE for Enterprise Java Developers 2019-03 R
    
- Maven 3.6.2
    

**Create a Eclipse Project using Spring Initializr**

- Go to [https://start.spring.io/](https://start.spring.io/)
    
- Change Group as “com.cognizant”
    
- Change Artifact Id as “orm-learn”
    
- In Options > Description enter "Demo project for Spring Data JPA and Hibernate"
    
- Click on menu and select "Spring Boot DevTools", "Spring Data JPA" and "MySQL Driver"
    
- Click Generate and download the project as zip
    
- Extract the zip in root folder to Eclipse Workspace
    
- Import the project in Eclipse "File > Import > Maven > Existing Maven Projects > Click Browse and select extracted folder > Finish"
    
- Create a new schema "ormlearn" in MySQL database. Execute the following commands to open MySQL client and create schema.
    

> mysql -u root -p

  
  

mysql> create schema ormlearn;

- In orm-learn Eclipse project, open src/main/resources/application.properties and include the below database and log configuration.
    

# Spring Framework and application log

logging.level.org.springframework=info

logging.level.com.cognizant=debug

  
  

# Hibernate logs for displaying executed SQL, input and output

logging.level.org.hibernate.SQL=trace

logging.level.org.hibernate.type.descriptor.sql=trace

  
  

# Log pattern

logging.pattern.console=%d{dd-MM-yy} %d{HH:mm:ss.SSS} %-20.20thread %5p %-25.25logger{25} %25M %4L %m%n

  
  

# Database configuration

spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

spring.datasource.url=jdbc:mysql://localhost:3306/ormlearn

spring.datasource.username=root

spring.datasource.password=root

  
  

# Hibernate configuration

spring.jpa.hibernate.ddl-auto=validate

spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.MySQL5Dialect

- Build the project using ‘mvn clean package -Dhttp.proxyHost=proxy.cognizant.com -Dhttp.proxyPort=6050 -Dhttps.proxyHost=proxy.cognizant.com -Dhttps.proxyPort=6050 -Dhttp.proxyUser=123456’ command in command line
    
- Include logs for verifying if main() method is called.
    

import org.slf4j.Logger;

import org.slf4j.LoggerFactory;

  
  

private static final Logger LOGGER = LoggerFactory.getLogger(OrmLearnApplication.class);

  
  

public static void main(String[] args) {

SpringApplication.run(OrmLearnApplication.class, args);

  LOGGER.info("Inside main");

}

- Execute the OrmLearnApplication and check in log if main method is called.
    

  
SME to walk through the following aspects related to the project created:

1. src/main/java - Folder with application code
    
2. src/main/resources - Folder for application configuration
    
3. src/test/java - Folder with code for testing the application
    
4. OrmLearnApplication.java - Walkthrough the main() method.
    
5. Purpose of @SpringBootApplication annotation
    
6. pom.xml
    
    1. Walkthrough all the configuration defined in XML file
        
    2. Open 'Dependency Hierarchy' and show the dependency tree.
        

**Country table creation**

- Create a new table country with columns for code and name. For sample, let us insert one country with values 'IN' and 'India' in this table.
    

create table country(co_code varchar(2) primary key, co_name varchar(50));

- Insert couple of records into the table
    

insert into country values ('IN', 'India');

insert into country values ('US', 'United States of America');

  
**Persistence Class - com.cognizant.orm-learn.model.Country**

- Open Eclipse with orm-learn project
    
- Create new package com.cognizant.orm-learn.model
    
- Create Country.java, then generate getters, setters and toString() methods.
    
- Include @Entity and @Table at class level
    
- Include @Column annotations in each getter method specifying the column name.
    

import javax.persistence.Column;

import javax.persistence.Entity;

import javax.persistence.Id;

import javax.persistence.Table;

  
  

@Entity

@Table(name="country")

public class Country {

  
  

  @Id

    @Column(name="code")

    private String code;

  
  

    @Column(name="name")

    private String name;

  
  

// getters and setters

  
  

  // toString()

  
  

}

_Notes:_

- @Entity is an indicator to Spring Data JPA that it is an entity class for the application
    
- @Table helps in defining the mapping database table
    
- @Id helps is defining the primary key
    
- @Column helps in defining the mapping table column
    

**Repository Class - com.cognizant.orm-learn.CountryRepository**

- Create new package com.cognizant.orm-learn.repository
    
- Create new interface named CountryRepository that extends JpaRepository<Country, String>
    
- Define @Repository annotation at class level
    

import org.springframework.data.jpa.repository.JpaRepository;

import org.springframework.stereotype.Repository;

  
  

import com.cognizant.ormlearn.model.Country;

  
  

@Repository

public interface CountryRepository extends JpaRepository<Country, String> {

  
  

}

**Service Class - com.cognizant.orm-learn.service.CountryService**

- Create new package com.cognizant.orm-learn.service
    
- Create new class CountryService
    
- Include @Service annotation at class level
    
- Autowire CountryRepository in CountryService
    
- Include new method getAllCountries() method that returns a list of countries.
    
- Include @Transactional annotation for this method
    
- In getAllCountries() method invoke countryRepository.findAll() method and return the result
    

**Testing in OrmLearnApplication.java**

- Include a static reference to CountryService in OrmLearnApplication class
    

private static CountryService countryService;

- Define a test method to get all countries from service.
    

    private static void testGetAllCountries() {

        LOGGER.info("Start");

        List<Country> countries = countryService.getAllCountries();

        LOGGER.debug("countries={}", countries);

        LOGGER.info("End");

    }

- Modify SpringApplication.run() invocation to set the application context and the CountryService reference from the application context.
    

        ApplicationContext context = SpringApplication.run(OrmLearnApplication.class, args);

        countryService = context.getBean(CountryService.class);

  
  

        testGetAllCountries();

- Execute main method to check if data from ormlearn database is retrieved.
**Difference between JPA, Hibernate and Spring Data JPA**   
  
Java Persistence API (JPA)

- JSR 338 Specification for persisting, reading and managing data from Java objects
    
- Does not contain concrete implementation of the specification
    
- Hibernate is one of the implementation of JPA
    

Hibernate

- ORM Tool that implements JPA
    

Spring Data JPA

- Does not have JPA implementation, but reduces boiler plate code
    
- This is another level of abstraction over JPA implementation provider like Hibernate
    
- Manages transactions
    

**Refer code snippets below on how the code compares between Hibernate and Spring Data JPA  
Hibernate**

   /* Method to CREATE an employee in the database */

   public Integer addEmployee(Employee employee){

      Session session = factory.openSession();

      Transaction tx = null;

      Integer employeeID = null;

      try {

         tx = session.beginTransaction();

         employeeID = (Integer) session.save(employee); 

         tx.commit();

      } catch (HibernateException e) {

         if (tx != null) tx.rollback();

         e.printStackTrace(); 

      } finally {

         session.close(); 

      }

      return employeeID;

   }

**Spring Data JPA**  
EmployeeRespository.java

public interface EmployeeRepository extends JpaRepository<Employee, Integer> {

  
  

}

EmployeeService.java

@Autowire

  private EmployeeRepository employeeRepository;

  
  

@Transactional

public void addEmployee(Employee employee) {

  employeeRepository.save(employee);

  }

​​​​​​​   
  
**Reference Links:**   
[https://dzone.com/articles/what-is-the-difference-between-hibernate-and-sprin-1](https://dzone.com/articles/what-is-the-difference-between-hibernate-and-sprin-1)   
[https://www.javaworld.com/article/3379043/what-is-jpa-introduction-to-the-java-persistence-api.html](https://www.javaworld.com/article/3379043/what-is-jpa-introduction-to-the-java-persistence-api.html)



**Create a Spring Web Project using Maven**   
  
Follow steps below to create a project:   
 

1. Go to [https://start.spring.io/](https://start.spring.io/)
    
2. Change Group as “com.cognizant”
    
3. Change Artifact Id as “spring-learn”
    
4. Select Spring Boot DevTools and Spring Web
    
5. Create and download the project as zip
    
6. Extract the zip in root folder to Eclipse Workspace
    
7. Build the project using ‘mvn clean package -Dhttp.proxyHost=proxy.cognizant.com -Dhttp.proxyPort=6050 -Dhttps.proxyHost=proxy.cognizant.com -Dhttps.proxyPort=6050 -Dhttp.proxyUser=123456’ command in command line
    
8. Import the project in Eclipse "File > Import > Maven > Existing Maven Projects > Click Browse and select extracted folder > Finish"
    
9. Include logs to verify if main() method of SpringLearnApplication.
    
10. Run the SpringLearnApplication class.
    

  
SME to walk through the following aspects related to the project created:

1. src/main/java - Folder with application code
    
2. src/main/resources - Folder for application configuration
    
3. src/test/java - Folder with code for testing the application
    
4. SpringLearnApplication.java - Walkthrough the main() method.
    
5. Purpose of @SpringBootApplication annotation
    
6. pom.xml
    
    1. Walkthrough all the configuration defined in XML file
        
    2. Open 'Dependency Hierarchy' and show the dependency tree.
        

  
  

**Hands on 2**

**Spring Core – Load SimpleDateFormat from Spring Configuration XML**   
  
SimpleDateFormat with the pattern ‘dd/MM/yyyy’ is created in multiple places of an application. To avoid creation of SimpleDateFormat in multiple places, define a bean in Spring XML Configuration file and retrieve the date.  
  
Follow steps below to implement:

- Create spring configuration file date-format.xml in src/main/resources folder of 'spring-learn' project
    
- Open https://docs.spring.io/spring-framework/docs/current/spring-framework-reference/core.html#beans-factory-metadata
    
- Copy the XML defined in the section of previous step URL and paste it into date-format.xml
    
- Define bean tag in the XML with for date format. Refer code below.
    

<?xml version="1.0" encoding="UTF-8"?>

<beans xmlns="http://www.springframework.org/schema/beans"

    xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"

    xsi:schemaLocation="http://www.springframework.org/schema/beans

        https://www.springframework.org/schema/beans/spring-beans.xsd">

  
  

<bean id="dateFormat" class="java.text.SimpleDateFormat">

<constructor-arg value="dd/MM/yyyy" />

</bean>

  
  

</beans>

- Create new method displayDate() in SpringLearnApplication.java
    
- In displayDate() method create the ApplicationContext. Refer code below:
    

ApplicationContext context = new ClassPathXmlApplicationContext("date-format.xml");

- Get the dateFormat using getBean() method. Refer code below.
    

SimpleDateFormat format = context.getBean("dateFormat", SimpleDateFormat.class);

- Using the format variable try to parse string '31/12/2018' to Date class and display the result using System.out.println.
    
- Run the application as 'Java Application' and check the result in console log output.
    

  
**Troubleshooting Tips**   
  
If the tomcat port has a conflict and the server is not starting include the below property in application.properties file in src/main/resources folder.



**Hello World RESTful Web Service**   
  
Write a REST service in the spring learn application created earlier, that returns the text "Hello World!!" using Spring Web Framework. Refer details below:  
  
**Method:** GET**URL:** /hello**Controller:** com.cognizant.spring-learn.controller.HelloController**Method Signature:** public String sayHello()**Method Implementation:** return hard coded string "Hello World!!"**Sample Request**: http://localhost:8083/hello  
**Sample Response:** Hello World!!   
  
**IMPORTANT NOTE**: Don't forget to include start and end log in the sayHello() method.  
  
Try the URL http://localhost:8083/hello in both chrome browser and postman.  
  
SME to explain the following aspects:

- In network tab of developer tools show the HTTP header details received
    
- In postman click on "Headers" tab to view the HTTP header details received
    

  
  

**REST - Country Web Service**   
  
Write a REST service that returns India country details in the earlier created spring learn application.  
  
**URL**: /country  
**Controller**: com.cognizant.spring-learn.controller.CountryController  
**Method Annotation**: @RequestMapping  
**Method Name**: getCountryIndia()  
**Method Implementation**: Load India bean from spring xml configuration and return  
**Sample Request**: http://localhost:8083/country  
**Sample Response**:

{

  "code": "IN",

  "name": "India"

}

  
SME to explain the following aspects:

- What happens in the controller method?
    
- How the bean is converted into JSON reponse?
    
- In network tab of developer tools show the HTTP header details received
    
- In postman click on "Headers" tab to view the HTTP header details received
    

  
  

**REST - Get all countries**   
  
Write a REST service that returns all the countries.  
  
**Controller**: com.cognizant.spring-learn.controller.CountryController  
**Method Annotation**: @GetMapping("/countries")  
**Method Name**: getAllCountries()  
**Method Implementation**: Load country list from country.xml and return  
  
**Sample Request**: http://localhost:8083/countries  
**Sample Response**:

[

  { "code": "IN", "name": "India"},

  { "code": "US", "name": "United States"},

  { "code": "JP", "name": "Japan"},

  { "code": "DE", "name": "Germany"}

]

  
  

**REST - Get country based on country code**   
  
Write a REST service that returns a specific country based on country code. The country code should be case insensitive.  
  
**Controller**: com.cognizant.spring-learn.controller.CountryController  
**Method Annotation:** @GetMapping("/countries/{code}")**Method Name**: getCountry(String code)  
**Method Implemetation**: Invoke countryService.getCountry(code)   
**Service Method:** com.cognizant.spring-learn.service.CountryService.getCountry(String code)  
  
**Service Method Implementation**:

- Get the country code using @PathVariable
    
- Get country list from country.xml
    
- Iterate through the country list
    
- Make a case insensitive matching of country code and return the country.
    
- Lambda expression can also be used instead of iterating the country list
    

**Sample Request**: http://localhost:8083/country/in  
  
**Sample Response**:

{

  "code": "IN",

  "name": "India"

}

week 4
**Create authentication service that returns JWT**   
  
As part of first step of JWT process, the user credentials needs to be sent to authentication service request that generates and returns the JWT.  
  
Ideally when the below curl command is executed that calls the new authentication service, the token should be responded. Kindly note that the credentials are passed using -u option.  
  
**Request**

curl -s -u user:pwd http://localhost:8090/authenticate

**Response**

{"token":"eyJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJ1c2VyIiwiaWF0IjoxNTcwMzc5NDc0LCJleHAiOjE1NzAzODA2NzR9.t3LRvlCV-hwKfoqZYlaVQqEUiBloWcWn0ft3tgv0dL0"}

  
This can be incorporated as three major steps:

- Create authentication controller and configure it in SecurityConfig
    
- Read Authorization header and decode the username and password
    
- Generate token based on the user retrieved in the previous step
    

Let incorporate the above as separate hands on exercises.


