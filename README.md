# Spring Boot WAR Deployment on External Tomcat 10

## Overview

This project demonstrates how to create a Spring Boot application packaged as a WAR file using only the Spring Web dependency. The WAR file can be deployed to an external Tomcat 10 server, allowing for easy deployment and management of your Spring Boot application.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Project Structure](#project-structure)
- [Configuration](#configuration)
- [Building the WAR File](#building-the-war-file)
- [Deploying to Tomcat](#deploying-to-tomcat)
- [Accessing the Application](#accessing-the-application)
- [License](#license)

## Prerequisites

Before you begin, ensure you have met the following requirements:

- **Java Development Kit (JDK)**: Version 11 or higher.
- **Apache Maven**: Version 3.6 or higher.
- **Apache Tomcat 10**: Download and install from [Apache Tomcat](https://tomcat.apache.org/).
- **Spring Boot**: This project uses Spring Boot 2.7.x or higher.


## Configuration

### `pom.xml`

Ensure your `pom.xml` is configured to package the application as a WAR file and includes the necessary dependencies:

```xml
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
    <modelVersion>4.0.0</modelVersion>
    <groupId>com.example</groupId>
    <artifactId>spring-boot-war-example</artifactId>
    <version>0.0.1-SNAPSHOT</version>
    <packaging>war</packaging>

    <properties>
        <java.version>11</java.version>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-tomcat</artifactId>
            <scope>provided</scope>
        </dependency>
    </dependencies>

    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
</project>
