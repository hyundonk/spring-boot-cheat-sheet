# spring-boot-cheat-sheet


## Generate spring boot application by using Spring Initializr
```
curl https://start.spring.io/starter.tgz -d dependencies=web,data-jdbc,mysql -d baseDir=demo-app -d bootVersion=2.3.4.RELEASE -d javaVersion=11 | tar -xzvf -
```

### Calling Rest API using curl
```
curl --header "Content-Type: application/json" \
    --request POST \
    --data '{"description":"configuration","details":"congratulations, you have set up JDBC correctly!","done": "true"}' \
    http://127.0.0.1:8080
```

### Using jdbc/r2dbc
- using jdbc with java
https://docs.microsoft.com/en-us/azure/mysql/connect-java

- using jdbc with spring boot
https://docs.microsoft.com/en-us/azure/developer/java/spring-framework/configure-spring-data-jdbc-with-azure-mysql?toc=/azure/mysql/toc.json&bc=/azure/bread/toc.json

- using jpa with spring boot
https://docs.microsoft.com/en-us/azure/developer/java/spring-framework/configure-spring-data-jpa-with-azure-mysql?toc=/azure/mysql/toc.json&bc=/azure/bread/toc.json

- using r2dbc with spring boot
https://docs.microsoft.com/en-us/azure/developer/java/spring-framework/configure-spring-data-r2dbc-with-azure-mysql?toc=/azure/mysql/toc.json&bc=/azure/bread/toc.json


### Using JPA
When loading Data to the database when application starts, refer below for "spring.datasource.initialization-mode" option
https://stackoverflow.com/questions/45082574/spring-boot-doesnt-load-data-to-initialize-database-using-data-sql

# Spring Tutorial

https://github.com/in28minutes/spring-master-class/tree/master/01-spring-in-depth

```
# Create a new spring project
curl "https://start.spring.io/starter.tgz?groupId=com.in28minutes.spring.basics&artifactId=spring-in-5-steps" -d baseDir=demo-app -d bootVersion=2.7.3 -d javaVersion=11 | tar -xzvf -

```



### Changing "java.configuration.runtimes" in Visual Studio Code with remote SSH
```
To edit the settings.json to add (or edit) the java.configuration.runtimes setting/s:

press CTRL+, (comma)
choose the correct "heading"/settings.json you are attempting to edit (i.e. user or specific workspace/s) (screenshot showing 3 environments)
type "java.configuration.runtimes" in the search box
if "No Settings Found" is returned, edit the settings.json file directly by clicking on the `Open Settings (JSON)' button near the top right of the window (as per above screenshot)
edit the appropriate settings.json and enter your customised java.configuration.runtimes snippet (as exemplified above), ensuring to use only the allowed "name"s (as mentioned above) and using the correct paths (taking into account if it is Windows or Linux paths - the latter applicable to WSL)

{
    "java.configuration.runtimes": [

        {
        "name": "JavaSE-11",
        "path": "/usr/lib/jvm/java-11-openjdk-amd64",
        },    
    ]
}

```


## Spring 특징
 - Dependency Injection - Spring Framework은 'bean'들을 관리하고 dependencies에 wiring을 수행. 사용자(개발자)가 직접 bean을 생성(new)할 필요가 없음
    - What are the beans?
    - What are the dependencies of a bean
    - Where to search for beans
 - Loosely Coupled
 - Autowiring은 constructor를 통하거나 setter를 통해 수행

### @SpringBootApplication
 Automatically scans application packages for dependency injection

 - Spring Application Context에서는 


 https://en.wikipedia.org/wiki/Enterprise_Integration_Patterns

 Why Spring is popular
  - Enables Testable Code
  - No Plumbing Code
  - Flexible Architecture
  - Staying Current



### Spring Framework in depth
 http://github.com/in28minutes/spring-master-class/tree/master/01-spring-in-depth

https://www.udemy.com/course/spring-tutorial-for-beginners/learn/lecture/7725718#overview


### Spring Boot 

#### Resolving multiple candidates for autowiring
- name
- primary
- @qualifier

### Bean Scope
 - 'Singletone' bean - Spring에서는 Application Context로 부터 Class에 대한 object을 요청하면 항상 같은 object을 return (by default)
 - 'prototypue' - 요청할 때마다 새로운 bean을 return
 - 'request' - One bean per HTTP request
 - 'session' - One bean per HTTP session
