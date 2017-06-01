Spring-test-webapp Documentation

1) Setting up the development machine

Install jdk ee
Install eclipse ee (tested on Eclipse Neon)
Install Maven Integration for Eclipse (if not already installed with your version of eclipse)
Install Spring IDE (if not installed STS version of eclipse)
 
Install Tomcat 7 (the application is tested with version 7)
Install MySQL Community Edition (there is a database.sql file in the project)
Install MySQL Workbench

2) Import to Eclipse 

The project is ready to be imported to Eclipse environment without any problem.
In order to Run the application on local server (Tomcat 7) it is important to configure
context.xml file of the server, through Eclipse. A copy of my context.xml is also uploaded
in the project. In this file there are the configurations for the server to connect the App
with the DB. Keep in mind that it is IMPORTANT to change the user and the password fields to 
match your local DB (and the url field, if another name is used!)

3) Remote server implemantation
Coming soon...