# Additional Topics

## Information Search

A typical way to search for information is to use search engines like Google,
Yahoo!, or Bing. The most popular one is Google; the name itself even became a
transitive verb. To google something means to search something using Google search
engine.

While it is very simple to use Google, there are several things which could help
you to get a better result:

- search on a specific site
- search for a specific file type
- exact match " "
- exclude words -
- or operator or

If you need information about a specific command line tool, sometimes it is better
to use built-in documentation for that tool rather than search the web. This
documentation is often called **man pages** (short for a manual page).

- Windows
  In Windows, this can be accessed by adding **"/?"** at the end of the command.
  For example, "ping /?". It shows what this command does, what arguments it accepts,
  and what flags can be used.

- Linux
  In Linux, short information about the command is shown by adding **"--help" or
  "--h"** at the end of the command. For example, "ping -h". Note that for some
  commands both options work well, while for others only one would work. The long
  version "—help" works in most cases.

## Software Licenses

You probably heard about open-source software and different names of licenses
like MIT license, Apache license, GNU GPL, BSD license. Let us give a short overview
of different types of licenses and their key restrictions.

A **software license** is a contract between the author of an application, source
code, or a related product, and its end user. Typical software describes whether
a user is permitted to use, modify, redistribute, and sublicense the software.

The two broad categories of software licenses are:

- **Proprietary** – also known as “closed source”. A typical proprietary software
  license gives a user rights to use the software, but it does not allow modification,
  redistribution, and sublicensing.
- **Free and open-source software (FOSS)** – also known as “open source”. Under
  the FOSS license, a user is typically allowed to use, modify, redistribute, and
  sometimes sublicense the software.

Comparison of Open Source and Proprietary Software

|                        |Proprietary Software|  Open Source Software                         |
|------------------------|--------------------|-----------------------------------------------|
|License Fee             |yes                 |  no                                           |
|Maintenance and Support |commercial support  |  community or commercial support, if available|
|Source Code Access      |no access           |  access, modification possible                |

It must be noted that software without any license should be considered as copyright
protected by default. Therefore, if there is no license included, software is legally
unusable in any way. The only exclusion to this rule is if software is placed in
the public domain by explicit note included in this software or because the rights
have expired or have been forfeited.

The proprietary licenses are not usually classified in any way because a software
owner may include almost any terms within their licenses to the extent it is not
against the law.

The FOSS licenses are often classified into two main categories:

- Copyleft – Other people can use, modify, and share their work based on licensed
  code if the new code is distributed under the same license.
- Permissive – Under this type of a license, there are a few restrictions on the
  distribution or modification of software. It allows proprietary derivative works
  if an appropriate license is included in the distribution.

The most popular FOSS licenses are:

- MIT License
- GNU General Public License (GPL)
- Apache License
- BSD License

Among these licenses, GNU GPL is the only copyleft license, the others are
permissive licenses. If you are working on a commercial proprietary project you
should never use GNU GPL licensed code in your work. However, even though software
released under permissive licenses allows you to use it in the proprietary projects,
you should consult with the team or project leads before doing so.

## Client-Server Model

A client makes a request for a service and receives a reply to that request; a
server receives and processes a request and sends back the required response.

Most client-server applications have three components:

- Presentation
  This is essentially a user interface. The presentation component is responsible
  for displaying information and sending user’s requests to the business logic
  component.

- Business Logic
  This is the software processing client’s requests. It coordinates the application
  and makes decisions.

- Data Storage
  The component responsible for storing and retrieving the data as requested by
  business logic. This is typically a database.

These components are separated into different tiers, or layers. Although the
words 'tier' and 'layer' are often used interchangeably, there is a difference
between them. A **layer** is a logical separation of the components that make
up a software. A **tier** is a physical separation of the components. An N-tier
architecture separates the components into different layers and tiers.

### 1-Tier Architecture

All components are kept on a single machine. Such design lacks scalability
because it runs on a single machine. The layers are tightly connected; changing
one layer often requires changing other layers. For example, the contacts app on
your phone has all three components, but it is a 1-tier architecture because
everything runs on your phone.

### 2-Tier Architecture

In a 2-Tier architecture, the business logic lives in the presentation tier. The
data storage is physically separated from the client in a different tier. It is
easy to switch to a different database if needed. The logic layer is still hard
to modify because it is tightly connected to the presentation layer.

### 3-Tier Architecture

Each layer runs on a separate machine. Presentation, logic, and data components
can be modified almost without affecting other layers.

Depending how much logic is built into the client, the clients can be classified:

- Thick clients
  It runs on a user’s computer and does most of computing using local resources.
  It can often work without network connection at all, or with limited connection.
  An example would be a game that runs on a computer and uses it resources heavily
  but also needs internet connection to interact with other people.

- Thin clients
  It relies on a server to do all computing and does not work offline. A typical
  example would be a web browser. They do not do anything on its own; however,
  by connecting to various web servers, they can provide a wide range of functionality.

## Introduction to DevOps

**DevOps** is a term that comes from combining the parts of words “development
and operations”. DevOps is a set of practices that bridges the gap between software
development and IT operations. Its primary goal is to build the development process
and infrastructure in such a way that new functionality of software is released
to customers more frequently, reliably, and properly tested at the same time.

The key concepts of DevOps are:

- Continuous integration:
  - Version control system
  - Build & integration Automation
- Continuous delivery:
  - Release Automation
  - Delivery Automation
  - Continuous deployment
  - Production Automation

**Continuous Integration** (CI) is a development practice where developers integrate
code into a shared repository frequently, at least one time a day. Automated tools
are used to assert the code being pushed to the repository.

Benefits and goals:

- Scale up headcount and delivery output of engineering teams. It minimizes the
  communication overhead between different teams. Every developer is working on
  the same version of code to make sure that the feature they are working on will
  smoothly integrate into the codebase.
- Faster feedback from product teams. The product team may review the result before
  a special release build is prepared for them to review.
- Harder to break the codebase. Issues are caught earlier using automated tests
  that run on every push of new code to the repository.
- Improves communication and collaboration. Since every developer is working on
  the up-to-date version of the code, they can see changes made by other developers
  and communicate if needed.

**Continuous Delivery** (CD) is an extension of continuous integration where code
changes can be deployed automatically to a testing or production environment after
the build stage.

Benefits and goals:

- Deploying software to a testing or production environment is a time-consuming
  task if done by hand. By using CI/CD tools this process is automated.
- Releases can be done more often. This allows the customer to give feedback faster.

**Continuous Deployment** (CD) is a fully-automated software release process. If
any changes made to the codebase pass the automated testing, the product is released
to the customers. Continuous deployment and continuous delivery are both abbreviated
as CD and may look similar because of the nomenclature. The key difference between
them is that in delivery, there is a manual approval step before production release.

Benefits and goals:

- The fastest possible releases to the customers.
- Easy-to-fix releases as the changes are very small.

### Tools for CI / CD

Software developers use various tools to automate testing and deliver the code
of their projects to end users. Let us describe the most efficient ones in the table
below.

Many teams which use CI / CD pipelines in the clouds use containers like **Docker**
and orchestration systems like **Kubernetes**. Containers help to standardize packaging
and delivery, and to simplify scaling and destruction of volatile environments.

Serverless computing architecture is another way to deploy and scale applications.
In a serverless environment, the infrastructure is completely managed by the
cloud provider, and the application consumes resources as needed according to its
settings.
