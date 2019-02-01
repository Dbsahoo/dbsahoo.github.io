---
layout: post
title:  "Microservice-SpringCloud-and-Netflix-Eureka"
author: sal
categories: [ Jekyll, tutorial ]
image: assets/images/17.jpg
---
Spring Cloud already supports both Eureka and Consul, though I’ll focus on Eureka in this post because it can be bootstrapped automatically in one of Spring Cloud’s auto-configurations. Eureka is implemented on the JVM but Consul is implemented in Go.

# Installing Eureka server
Standing up an instance of the Eureka service registry is easy if you have 
> org.springframework.boot:spring-cloud-starter-eureka-server on your classpath.

```java
package registry;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;
import org.springframework.cloud.netflix.eureka.server.EnableEurekaServer;

@SpringBootApplication
@EnableEurekaServer
public class Application {

  public static void main(String[] args) {
    SpringApplication.run(Application.class, args);
  }
}
```
