---
layout: post
title:  "Microservices Routing and Filtering"
author: sal
categories: [ Jekyll, tutorial ]
image: assets/images/12.jpg
featured: true
hidden: true
---

Router and Filter: Zuul

Overview

The goal is to work around CORS and the Same Origin Policy restriction of the browser and allow the UI to call the API even though they don’t share the same origin.
We’ll basically create two separate applications – a UI application and a simple REST API, and we’ll use the Zuul proxy in the UI application to proxy calls to the REST API.
Zuul is a JVM based router and server side load balancer by Netflix. And Spring Cloud has a nice integration with an embedded Zuul proxy .

Maven Configuration

```ruby
<dependency>
    <groupId>org.springframework.cloud</groupId>
    <artifactId>spring-cloud-starter-zuul</artifactId>
    <version>1.0.4.RELEASE</version>
</dependency>
```

Zuul Properties for Routing

```ruby
zuul:
  routes:
    foos:
      path: /service/API/**
      url: http://localhost:8081/spring-zuul-foos-resource/foos
```

Application should be annotate with @EnableZuulProxy

Spring Cloud Netflix includes an embedded Zuul proxy, which we can enable with the @EnableZuulProxy annotation. 
This will turn the Gateway application into a reverse proxy that forwards relevant calls to other services

```java
@EnableZuulProxy
@SpringBootApplication
public class GatewayApplication {

  public static void main(String[] args) {
    SpringApplication.run(GatewayApplication.class, args);
  }

}
```

Types of ZuulFilter 

```

	_pre_ filters are executed before the request is routed,
	
	_route_ filters can handle the actual routing of the request,
	
	_post_ filters are executed after the request has been routed, and
	
	_error_ filters execute if an error occurs in the course of handling the request.

```

Sample pre ZuulFilter
```java
package hello.filters.pre;

import javax.servlet.http.HttpServletRequest;
import com.netflix.zuul.context.RequestContext;
import com.netflix.zuul.ZuulFilter;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class SimpleZuulFilter extends ZuulFilter {

  private static Logger log = LoggerFactory.getLogger(SimpleFilter.class);

  @Override
  public String filterType() {
    return "pre";
  }

  @Override
  public int filterOrder() {
    return 1;
  }

  @Override
  public boolean shouldFilter() {
    return true;
  }

  @Override
  public Object run() {
    RequestContext ctx = RequestContext.getCurrentContext();
    HttpServletRequest request = ctx.getRequest();

    log.info(String.format("%s request to %s", request.getMethod(), request.getRequestURL().toString()));

    return null;
  }

}
```

Sample route ZuulFilter
```java
package hello.filters.pre;

import javax.servlet.http.HttpServletRequest;
import com.netflix.zuul.context.RequestContext;
import com.netflix.zuul.ZuulFilter;

import org.slf4j.Logger;
import org.slf4j.LoggerFactory;

public class SimpleZuulFilter extends ZuulFilter {

  private static Logger log = LoggerFactory.getLogger(SimpleFilter.class);

  @Override
  public String filterType() {
    return "route";
  }

  @Override
  public int filterOrder() {
    return 1;
  }

  @Override
  public boolean shouldFilter() {
    return true;
  }

  @Override
  public Object run() {
     String requestUri = RequestContext.getCurrentContext().getRequest().getRequestURI();
       for (Route route : routeLocator.getRoutes()) {
        String serviceUrl = route.getFullPath();
        String serviceName = route.getId();
       if (requestUri.startsWith(serviceUrl.substring(0, serviceUrl.length() - 2))) {
		return !isAuthorizedRequest(serviceUrl, serviceName, requestUri);
        }
    }
    return true;
  }

}
```

Refer Video for complete Demo

<p><iframe width="560" height="315" src="https://www.youtube.com/embed/-IOBubnPgfg" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe></p>
	
	
	
Provide comments and post questions,Thanks...
