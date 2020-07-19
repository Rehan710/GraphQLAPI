# GraphQLAPI
Creating a GraphQL API that returns a list of dogs from an embedded H2 in memory database.

Set Up
Step 1: Use Spring Initializr to bootstrap a simple project.

Add the H2 Database, Spring Web Starter, and the Spring Data JPA dependencies before generating the project.

Step 2: Add the necessary GraphQL dependencies manually in your Maven POM file.

You will need to manually enter these in your Maven POM file.
Set up the necessary H2 and GraphQL properties to application.properties at this time as well.

First, add the following dependencies in the pom.xml file:

<dependency>
            <groupId>com.graphql-java</groupId>
            <artifactId>graphql-spring-boot-starter</artifactId>
            <version>5.0.2</version>
        </dependency>

        <dependency>
            <groupId>com.graphql-java</groupId>
            <artifactId>graphql-java-tools</artifactId>
            <version>5.2.4</version>
        </dependency>

        <dependency>
            <groupId>com.graphql-java</groupId>
            <artifactId>graphiql-spring-boot-starter</artifactId>
            <version>5.0.2</version>
        </dependency>
        
Then, head over to your application.properties and add the following:

spring.h2.console.enabled=true
spring.h2.console.path=/h2
spring.datasource.url=jdbc:h2:mem:dogdata

graphql.servlet.mapping=/graphql
graphql.servlet.enabled=true
graphql.servlet.corsEnabled=true

graphiql.enabled=true
graphiql.endpoint=/graphql
graphiql.mapping=graphiql


