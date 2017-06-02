# Spring-test-webapp 

This is a test project i made to teach my self the Java Spring Framework. 
The idea for this project is to create a site where anyone has the ability to create an account and post a job advert. Then any visitor can view the job adverts and send a message to the applicants. The applicants have the ability to respond to those messages and an email is sent to the visitor who sent the message.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes. See deployment for notes on how to deploy the project on a live system.

### Prerequisites

```
The version of Eclipse that it was used for the development is Eclipse Neon on MacOS Sierra 10.12.5
The version of the server used is Tomcat 7
```
### Installing
```
Install jdk ee 
Install eclipse ee 
Install Maven Integration for Eclipse 
Install Spring IDE 
 
Install Tomcat 7 
Install MySQL Community Edition (there is a database.sql file in the project)
Install MySQL Workbench
```

### Import to Eclipse 

The project is ready to be imported to Eclipse environment without any problem.
In order to Run the application on local server (Tomcat 7) it is important to configure
context.xml file of the server, through Eclipse. A copy of my context.xml is also uploaded
in the project. In this file there are the configurations for the server to connect the App
with the DB. Keep in mind that it is IMPORTANT to change the user and the password fields to 
match your local DB (and the url field, if another name is used!)

```
<Resource name="jdbc/spring" auth="Container" type="javax.sql.DataSource"
		maxActive="100" maxIdle="30" maxWait="10000" username="root"
		password="123456" driverClassName="com.mysql.jdbc.Driver"
		url="jdbc:mysql://localhost:3306/springtutorial" />
```

### Database
In the project there is a database.sql file which contains the SQL commands to create a DB with the proper tables for the application. Also with the tables, an Administrator user is created with username: Administrator and password: 123456789 (you can delete this user if you like and create an new one but you have to remember that it's IMPORTANT to give this user authority: ROLE_ADMIM manually!)

### Email responses
In order to set up the application properly so it can sent emails, you have to create a developer email account (Gmail) and configure the following file (/WebContent/WEB-INF/offers-servlet)

```
<bean id="mailSender" class="org.springframework.mail.javamail.JavaMailSenderImpl">
		<property name="host" value="smtp.gmail.com"/>
		<property name="port" value="587"/>
		<property name="username" value="usernmae@gmail.com"/>
		<property name="password" value="password"/>
		<property name="javaMailProperties">
			<props>
				<prop key="mail.smtp.auth">true</prop>
				<prop key="mail.smtp.starttls.enable">true</prop>
				<prop key="mail.smtp.ssl.trust">smtp.gmail.com</prop>
			</props>
		</property>
		
	</bean>
```	

### Deployment
After importing the project to your local machine and test it, in order to deploy the app to a real server you have to follow those steps to your remote server:

Install Tomcat 7 (to run the app)
Install MySQL (to store your data)
Install vsftp (to transfer files to your server)

After the installations are done

1) Configure Tomcat manager panel and create an admin user
2) Configure Tomcat's context.xml  

```
<Resource name="jdbc/spring" auth="Container" type="javax.sql.DataSource"
		maxActive="100" maxIdle="30" maxWait="10000" username="root"
		password="123456" driverClassName="com.mysql.jdbc.Driver"
		url="jdbc:mysql://localhost:3306/springtutorial" />
```


3) Create the Database for the app by following the SQL commands of the database.sql file
4) Through your local machine, export a WAR file of the project
5) Deploy the WAR file using tomcat's manager web interface


## Built With

* [Eclipse NEO](http://www.eclipse.org/neon/) - Java IDE
* [Spring](https://projects.spring.io/spring-framework/) - Web Framework
* [Hibernate](http://hibernate.org) - Data Framework
* [Maven](https://maven.apache.org/) - Dependency Management
* [MySQL](https://dev.mysql.com/downloads/) - RDBMS
* [Apache Tomcat 7](https://tomcat.apache.org/download-70.cgi) - Web Server

## Authors

* **Axilleas Moukoulis** - *Initial work* - [AxilleasMoukoulis](https://github.com/AxilleasMoukoulis)

## Acknowledgments

* The project is based on the Udemy course [The Java Spring Tutorial: Learn Java's Popular Web Framework](https://www.udemy.com/javaspring/learn/v4/overview)
* Instructor: John Purcell
