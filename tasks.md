**Exercise 1: Implementing the Singleton Pattern**

**Scenario:**

You need to ensure that a logging utility class in your application has only one instance throughout the application lifecycle to ensure consistent logging.

**Steps:**

1. **Create a New Java Project:**
    
    - Create a new Java project named **SingletonPatternExample**.
        
2. **Define a Singleton Class:**
    
    - Create a class named Logger that has a private static instance of itself.
        
    - Ensure the constructor of Logger is private.
        
    - Provide a public static method to get the instance of the Logger class.
        
3. **Implement the Singleton Pattern:**
    
    - Write code to ensure that the Logger class follows the Singleton design pattern.
        
4. **Test the Singleton Implementation:**
    
    - Create a test class to verify that only one instance of Logger is created and used across the application.


**Exercise 2: Implementing the Factory Method Pattern**

**Scenario:**

You are developing a document management system that needs to create different types of documents (e.g., Word, PDF, Excel). Use the Factory Method Pattern to achieve this.

**Steps:**

1. **Create a New Java Project:**
    
    - Create a new Java project named **FactoryMethodPatternExample**.
        
2. **Define Document Classes:**
    
    - Create interfaces or abstract classes for different document types such as **WordDocument**, **PdfDocument**, and **ExcelDocument**.
        
3. **Create Concrete Document Classes:**
    
    - Implement concrete classes for each document type that implements or extends the above interfaces or abstract classes.
        
4. **Implement the Factory Method:**
    
    - Create an abstract class **DocumentFactory** with a method **createDocument()**.
        
    - Create concrete factory classes for each document type that extends DocumentFactory and implements the **createDocument()** method.
        
5. **Test the Factory Method Implementation:**
    
    - Create a test class to demonstrate the creation of different document types using the factory method.



**Exercise 2: E-commerce Platform Search Function**

**Scenario:**

You are working on the search functionality of an e-commerce platform. The search needs to be optimized for fast performance.

**Steps:**

1. **Understand Asymptotic Notation:**
    
    - Explain Big O notation and how it helps in analyzing algorithms.
        
    - Describe the best, average, and worst-case scenarios for search operations.
        
2. **Setup:**
    
    - Create a class **Product** with attributes for searching, such as **productId, productName**, and **category**.
        
3. **Implementation:**
    
    - Implement linear search and binary search algorithms.
        
    - Store products in an array for linear search and a sorted array for binary search.
        
4. **Analysis:**
    
    - Compare the time complexity of linear and binary search algorithms.
        
    - Discuss which algorithm is more suitable for your platform and why.

**Exercise 7: Financial Forecasting**

**Scenario:**

You are developing a financial forecasting tool that predicts future values based on past data.

**Steps:**

1. **Understand Recursive Algorithms:**
    
    - Explain the concept of recursion and how it can simplify certain problems.
        
2. **Setup:**
    
    - Create a method to calculate the future value using a recursive approach.
        
3. **Implementation:**
    
    - Implement a recursive algorithm to predict future values based on past growth rates.
        
4. **Analysis:**
    
    - Discuss the time complexity of your recursive algorithm.
        
    - Explain how to optimize the recursive solution to avoid excessive computation.

**Exercise 1: Control Structures**

  

**Scenario 1:** The bank wants to apply a discount to loan interest rates for customers above 60 years old.

- **Question:** Write a PL/SQL block that loops through all customers, checks their age, and if they are above 60, apply a 1% discount to their current loan interest rates.
    

**Scenario 2:** A customer can be promoted to VIP status based on their balance.

- **Question:** Write a PL/SQL block that iterates through all customers and sets a flag IsVIP to TRUE for those with a balance over $10,000.
    

**Scenario 3:** The bank wants to send reminders to customers whose loans are due within the next 30 days.

- **Question:** Write a PL/SQL block that fetches all loans due in the next 30 days and prints a reminder message for each customer.

**Exercise 3: Stored Procedures**

  

**Scenario 1:** The bank needs to process monthly interest for all savings accounts.

- **Question:** Write a stored procedure **ProcessMonthlyInterest** that calculates and updates the balance of all savings accounts by applying an interest rate of 1% to the current balance.
    

  

**Scenario 2:** The bank wants to implement a bonus scheme for employees based on their performance.

- **Question:** Write a stored procedure **UpdateEmployeeBonus** that updates the salary of employees in a given department by adding a bonus percentage passed as a parameter.
    

  

**Scenario 3:** Customers should be able to transfer funds between their accounts.

- **Question:** Write a stored procedure **TransferFunds** that transfers a specified amount from one account to another, checking that the source account has sufficient balance before making the transfer.





Exercise 1: Setting Up JUnit
Scenario:
You need to set up JUnit in your Java project to start writing unit tests.
Steps:
1. Create a new Java project in your IDE (e.g., IntelliJ IDEA, Eclipse).
2. Add JUnit dependency to your project. If you are using Maven, add the following to your
pom.xml:
<dependency>
<groupId>junit</groupId>
<artifactId>junit</artifactId>
<version>4.13.2</version>
<scope>test</scope>
</dependency>
3. Create a new test class in your project.


Exercise 3: Assertions in JUnit
Scenario:
You need to use different assertions in JUnit to validate your test results.
Steps:
1. Write tests using various JUnit assertions.
Solution Code:
public class AssertionsTest {
@Test
public void testAssertions() {
// Assert equals
assertEquals(5, 2 + 3);
// Assert true
assertTrue(5 > 3);
// Assert false
assertFalse(5 < 3);
// Assert null
assertNull(null);
}
// Assert not null
assertNotNull(new Object());
}



Exercise 4: Arrange-Act-Assert (AAA) Pattern, Test Fixtures, Setup and
Teardown Methods in JUnit
Scenario:
You need to organize your tests using the Arrange-Act-Assert (AAA) pattern and use setup
and teardown methods.
Steps:
1. Write tests using the AAA pattern.
2. Use @Before and @After annotations for setup and teardown methods.






Exercise 1: Mocking and Stubbing
Scenario:
You need to test a service that depends on an external API. Use Mockito to mock the
external API and stub its methods.
Steps:
1. Create a mock object for the external API.
2. Stub the methods to return predefined values.
3. Write a test case that uses the mock object.
Solution Code:
import static org.mockito.Mockito.*;
import org.junit.jupiter.api.Test;
import org.mockito.Mockito;
public class MyServiceTest {
@Test
public void testExternalApi() {
ExternalApi mockApi = Mockito.mock(ExternalApi.class);
when(mockApi.getData()).thenReturn("Mock Data");
MyService service = new MyService(mockApi);
String result = service.fetchData();
assertEquals("Mock Data", result);
}
}
Exercise 2: Verifying Interactions
Scenario:
You need to ensure that a method is called with specific arguments.
Steps:
4. Create a mock object.
5. Call the method with specific arguments.
6. Verify the interaction.
Solution Code:
import static org.mockito.Mockito.*;
importimportorg.junit.jupiter.api.Test;
org.mockito.Mockito;
public class MyServiceTest {
@Test
public void testVerifyInteraction() {
ExternalApi mockApi = Mockito.mock(ExternalApi.class);
MyService service = new MyService(mockApi);
service.fetchData();
verify(mockApi).getData();
}
}



-week-2------------------


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
        
3. **Test the Configuration:**
4. - Run the **LibraryManagementApplication** main class to verify the dependency injection.


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




**Hands on 4**

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
  


