# Containers and Serverless

## Containers

A **container** is a standard unit of software that packages up code and all its
dependencies so that an application runs quickly and reliably from one computing
environment to another. A container image is a lightweight, stand-alone, executable
package of software that includes everything needed to run an application: code,
runtime, system tools, system libraries and settings. Containers are designed to
make the DevOps process simple and efficient.

### Doker

Docker Engines

The Docker Engine combines open-source container technology with a workflow for
building, running, and managing containerized applications. The Docker Engine
consists of three major components:

- Docker Daemon

  A service running on the host computer that executes commands. It manages Docker
  images, containers, networks, and storage volumes.

- Rest API

  An API used by applications to execute Docker commands via the Docker daemon.

- Docker CLI

  A command-line interface developers use to execute Docker commands via the Docker
  daemon.

#### Kubernetes

Like Docker, Kubernetes is the most popular orchestration system in the industry.
Kubernetes is an open-source container orchestration platform designed to automate
deployment, scaling and management of application software in containers. You can
run Kubernetes clusters yourself, but you should have specific skills to do that.
To simplify container adoption, it is becoming increasingly popular to use a Kubernetes
service run by one of the cloud providers in a SaaS model.

Kubernetes creates an abstraction layer that performes key functions and allows
the development team to concentrate on the application functionality.

## Serverless

Imagine deploying an application without having to think about server management.
Serverless technology makes this possible. Serverless computing provides a way to
quickly evolve architecture while placing minimal emphasis—if any at all—on
physical infrastructure.

Serverless architecture is powered by cloud service companies and is used to build
scalable, cost-efficient applications that allow you to increase agility and
decrease the need to support legacy hardware and operating systems.

However, "serverless" doesn't mean there are no physical parts to this architecture.
Technically, there is a server somewhere; you just do not have to think about it.
The term "serverless" implies that developers and application teams do not need to
concern themselves with the building, deployment, configuration, and operational
management of underlying infrastructure. They can build their programs for nearly
any type of application, and everything required to run and scale the application
with high availability is handled for them by the cloud management vendor.

## 12-Factor App

This massive demand has caused software engineers to respond with new software
development strategies—hence the emergence of the 12 factors of cloud-native
application development. It can be applied to apps written in any language and
using any combination of backing services.

1.Codebase
   Each web app should have a single codebase with tracked version control.

2.Dependencies
   Dependencies should be explicitly declared and isolated. Dependencies should
   not be in the codebase but instead use a package manager.

3.Config
   You should separate config and code. The code remains the same, no matter where
   you deploy the application.

4.Backing Services
   To ensure portability, you should be able to easily change from one backing service
   provider to another without any code changes.

5.Build, Release, Run
   You should separate the build, release, and run stages, with each release having
   a unique ID and allowing rollback.

6.Stateless Processes
   Applications should be able to execute as a single, stateless process.

7.Port Binding
   Services should be visible and self-contained via port-binding and shared object
   libraries.

8.Concurrency
   Rather than running a single instance of your application on your most powerful
   machine, you should break your app into smaller processes that can be scaled
   individually.

9.Disposability
   You should be able to run and stop processes quickly and handle failure.

10.Development and Production Parity
    Development, staging, and production environments should be as similar as possible
    to limit deviation and error.

11.Logs
    You should capture logs as continuous event streams that are performed by a
    separate service.

12.Admin Processes
    Admin tasks should be one-off and run via the app’s codebase.

## Cloud-Native Applications

To put it simply, it is a program (or suite of programs) that is designed specifically
for a cloud computing architecture.

Cloud-native applications are designed to take advantage of cloud computing frameworks
and styles of architecture, which are composed of loosely coupled cloud services.
That means architects and developers must break down applications into separate
services that can run and be updated independently. Therefore, these applications
must be designed and implemented with resilience in mind so they can withstand
failures or interruptions in other services within the application, as well as
the possibility of cloud resource failures, or even cloud region failures.





