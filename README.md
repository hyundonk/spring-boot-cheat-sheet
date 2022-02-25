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
