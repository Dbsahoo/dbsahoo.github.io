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

