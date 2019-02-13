---
layout: post
title:  "Microservice-SpringCloud-and-Netflix-Eureka"
author: sal
categories: [ java, spring ]
image: assets/images/Eureka.jpg
---
Spring Cloud already supports both Eureka and Consul, though we'll focus on Eureka in this post.

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

Application.yml configuration lokks like below 

```
server:
  port: ${PORT:8761}

eureka:
  client:
    registerWithEureka: false
    fetchRegistry: false
    server:
      waitTimeInMsWhenSyncEmpty: 0
```

The service’s port is defaulted to the well-known 8761 ,
you can point a browser to http://localhost:8761 and monitor the registry from there.


# Installing Eureka Client

```java
@SpringBootApplication
@EnableEurekaClient
@EnableFeignClients
public class Application {

    public static void main(String[] args) {
        SpringApplication.run(Application.class, args);
    }
}
```

# For complete demo please refer below video 

<p><iframe width="100%" height="315" src="https://www.youtube.com/embed/KfsQT3DsLdo" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>

