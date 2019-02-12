---
layout: post
title:  "Spring-Cloud-Microservices"
author: john
categories: [java,spring]
image: assets/images/springCloud.jpg
featured: true
hidden: true
---
Demo spring cloud with Spring Boot

> Spring Cloud provides tools for developers to quickly build some of the common patterns in distributed systems (e.g. configuration management, service discovery, circuit breakers, intelligent routing, micro-proxy, control bus, one-time tokens, global locks, leadership election, distributed sessions, cluster state). 

> Coordination of distributed systems leads to boiler plate patterns, and using Spring Cloud developers can quickly stand up services and applications that implement those patterns. They will work well in any distributed environment, including the developer’s own laptop, bare metal data centres, and managed platforms such as Cloud Foundry.

## Spring Cloud & Microservices

Spring Cloud focuses on providing good out of box experience for typical use cases and extensibility mechanism to cover others.

> Distributed/versioned configuration
> Service registration and discovery
> Routing
> Service-to-service calls
> Load balancing
> Circuit Breakers
> Global locks
> Leadership election and cluster state
> Distributed messaging

### different challenges arise when we take on a microservice approach:

> Externalizing configuration so that is flexible and does not require rebuild of the service on change
> Service discovery
> Hiding complexity of services deployed on different hosts

### Required Dependencies for common spring cloud features 

```ruby
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-config</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-eureka</artifactId>
</dependency>
<dependency>
    <groupId>org.springframework.boot</groupId>
    <artifactId>spring-boot-starter-web</artifactId>
</dependency>
```

### Refer below videos for complete demo on Spring cloud ...


<p><iframe width="100%" height="315" src="https://www.youtube.com/embed/TBM2NQlahTw" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>
