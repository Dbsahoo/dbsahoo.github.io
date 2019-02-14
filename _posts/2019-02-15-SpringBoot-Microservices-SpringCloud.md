---
layout: post
title:  "SpringBoot-Microservice-SpringCloud"
author: sal
categories: [ java, spring ]
image: assets/images/zuul.jpg
---



# Microservice Architecture Overview
Most of the applications we have so far are Monolithic applications , A monolithic application is build using one big unit of code and all the code in the monolithic application is tightly coupled, code base grows as we add new features to the monolithic app, over time it can be difficult to know where a change needs to be made because of the code grows too large , despite of modularity in Monolithic code bases , it is hard to make the code with the boundaries of the business functionality , code related to similar functions start become to spread all over , making bug fixes or new implementations becomes more difficult.

Unlike Monolithic applications , Micro services are small autonomous components that are loosely coupled and created with in bounded context that work together to create a specific business functionality, Micro services architectural style is an extension of service oriented Architecture , it is an approach to developing a single application as a suite of small services each running its own process and communicating with lightweight mechanisms , these services are built around business capabilities by following domain driven principals and independently deployable using some automated deployment process.

## Characteristics of micro services:

- Small autonomous web applications
- Each running in its own process
- Lightweight communication mechanism
- Built around business capabilities
- Independently deployable
- Minimum of centralized management
- Stateless
- Resilient (Design for failure)
- Single Responsibility Principle

## Micro app Principles:
Micro app architectural style follows 12 factor app design principles, below are the 12 design principles of a Micro app.

- One Code Base /Many deploys
- Explicitly isolate dependencies
- Configuration via Environment
- Stateless Processes
- Separate Build/release/run
- Scale Out
- Export services Via port binding
- Backend services as attached resources
- Disposable instances
- Keep Development ,test, staging and production as similar as possible
- Treat logs as event streams
- Run admin/Management process as one of processes



## Bestfit Java Microservice Technology Stack
One of the advantages of architecting your application in this style is that Micro services aren’t tied to a particular technology stack. This gave us the flexibility to choose technologies instead of defaulting to a technology that may or may not make sense. Java based technologies have been choosed primarily to implement micro services.
Below is the technology quadrant where all the techniques, tools, platforms and frameworks are being considered for building micro services.

**Java 8**
Java 8 has lot of new features that can improve the developer productivity and the performance , also it support parallel processing , below are the some of the new features that java 8 has.

- Lambda Expressions, a new language feature, has been introduced in this release. They enable you to treat functionality as a method argument, or code as data. Lambda expressions let you express instances of single-method interfaces (referred to as functional interfaces) more compactly.
- Method references provide easy-to-read lambda expressions for methods that already have a name.
- Default methods enable new functionality to be added to the interfaces of libraries and ensure binary compatibility with code written for older versions of those interfaces.
- Repeating Annotations provide the ability to apply the same annotation type more than once to the same declaration or type use.
- Type Annotations provide the ability to apply an annotation anywhere a type is used, not just on a declaration. Used with a pluggable type system, this feature enables improved type checking of your code.
- Improved type inference.
- Method parameter reflection.
- Classes in the new java.util.stream package provide a Stream API to support functional-style operations on streams of elements. The Stream API is integrated into the Collections API, which enables bulk operations on collections, such as sequential or parallel map-reduce transformations.
- Performance Improvement for HashMaps with Key Collisions

## Spring boot

Spring boot  is designed to simplify the bootstrapping and development of a new Spring application. The framework takes an opinionated approach to configuration, freeing developers from the need to define boilerplate configuration and code, the goal of Spring Boot is not to provide new solutions for the many problem domains already solved, but rather to leverage the platform in fostering a development experience that simplifies the use of those already-available technologies. Some of the features are.

- Create stand-alone Spring applications
- Embed Tomcat, Jetty or Undertow directly (no need to deploy WAR files)
- Provide opinionated 'starter' POMs to simplify your Maven configuration
- Automatically configure Spring whenever possible
- Provide production-ready features such as metrics, health checks and externalized configuration
- Absolutely no code generation and no requirement for XML configuration

## Spring boot web
Spring web framework provides annotations for  applications to create rest based apis , applications can create asynchronous rest apis using web async  manager or leave then synchronous, please refer to Serction 4.2 for more information on how to create apis.

## Undertow 
Undertow is a flexible performant web server written in java, providing both blocking and non-blocking API’s based on NIO.
Undertow has a composition based architecture that allows you to build a web server by combining small single purpose handlers. The gives you the flexibility to choose between a full Java EE servlet 3.1 container, or a low level non-blocking handler, to anything in between.
Undertow is designed to be fully embeddable, with easy to use fluent builder APIs. Undertow’s lifecycle is completely controlled by the embedding application.

## Gemfire
Gemfire Also referred to as an in-memory data grid, Gemfire (EDF) is a distributed, memory-based data management platform that uses cluster-wide resources – memory, CPU, network bandwidth, and optionally local disk – to manage application data and application logic (behavior). The Gemfire uses dynamic replication and data partitioning techniques to offer continuous availability, very high performance, and linear scalability for data intensive applications, all without compromising on data consistency even when exposed to failure conditions. Application logic execution can be parallelized by moving behavior to the data nodes or the data to the behavior. Also, clients can subscribe to data changes in the Gemfire for reliable, asynchronous event notifications enabling event driven architecture.

**GemFire in a Nutshell**

- Memory Oriented
- Object or JSON Database
- Schemaless or Rich Objects
- Puts and Gets / Object Query Language
- Shared Nothing
- Horizontally Scaling
- Globally Distributed 

**GemFire Features Summary**
- Rich Objects
- Ultra-Low Laatency RAM Durability
- Elastic Growth w/o pausing
- Partitioned Active Data
- Redundancy for instant FT
- Colocated Active Data
- Replicated Master Data
- Ultra-fast Colocated Transactions 
- Server-side Event Listeners
- Client-side Durable Subscriptions
- Parallel Map-Reduce Function Execution
- Parallel OQL Queries
- Continuous Queries
- LRU Overflow to disk in native format for fast retrieval
- Parallel, Shared Nothing Persistence to disk w/ online backup 
- Synchronous or Asynchronous Write Through, Read Through
- Uni or Bi-directional cluster synchronization over WAN






 



