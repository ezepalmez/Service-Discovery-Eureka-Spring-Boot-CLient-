# Service-Discovery-Eureka-Spring-Boot-Client
Service Discovery-Eureka &amp; Spring Boot-Client

# discovery-service-server-eureka
pom.xml
```bash
<properties>
        <java.version>1.8</java.version>
        <spring-cloud.version>Hoxton.SR3</spring-cloud.version>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-netflix-eureka-server</artifactId>
        </dependency>
    </dependencies>

    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.cloud</groupId>
                <artifactId>spring-cloud-dependencies</artifactId>
                <version>${spring-cloud.version}</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
 ```   
 application.properties
```bash
        # Spring config
        spring.application.name:discovery-service
        eureka.instance.hostname=127.0.0.1 

        # Eureka config
        eureka.client.register-with-eureka=false
        eureka.client.fetch-registry=false
        eureka.environment=prod

        # deploy Server 
        eureka.client.serviceUrl.defaultZone: http://127.0.0.1:19999/eureka/
```  
# demo-eureka-client
pom.xml
```bash
<properties>
        <java.version>1.8</java.version>
        <spring-cloud.version>Hoxton.SR3</spring-cloud.version>
    </properties>

    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
        <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-netflix-eureka-client</artifactId>
        </dependency>
    </dependencies>

    <dependencyManagement>
        <dependencies>
            <dependency>
                <groupId>org.springframework.cloud</groupId>
                <artifactId>spring-cloud-dependencies</artifactId>
                <version>${spring-cloud.version}</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
        </dependencies>
    </dependencyManagement>
```
```bash
        # Spring config
        spring.application.name=demo-eureka-client

        # Eureka server
        eureka.client.serviceUrl.defaultZone: http://localhost:19999/eureka/
``` 
