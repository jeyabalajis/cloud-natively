# Cloud Natively

Hello there! Welcome to this portal. The intent of this portal is to provide you with a comprehensive overview of what a cloud native application is, it's effects on making software delivery better and also details how you can approach building cloud native applications.

We start with a high level overview of what a _Cloud Native_ software application is, and then delve deeper into the various constituents. Hope you enjoy this guide!

> Cloud Natively - A comprehensive overview of Cloud Native applications

## What is Cloud Native?

Cloud Native applications allow your organization to ship faster, reduce risk, and grow your business.

> Cloud native is an approach to building and running applications that exploits the advantages of the cloud computing delivery model. When companies build and operate applications using a cloud native architecture, they bring new ideas to market faster and respond sooner to customer demands.

> Cloud Native is the answer to the software industry’s relentless search in the current decade for a set of tools and practices that makes your software easily deployable, modular, maintainable, robust, reliable, scalable, portable and observable — all at once.

Under the hood, a Cloud Native architecture is supported by these key architecture patterns and processes.

![Cloud Native Components](./images/cloud_native_composition.png)

### Containers

> Containers are a great enabler of Cloud Native software.

Containerization is the first step towards making your software portable to cloud & scalable thereof. 

- Containerization is normally done with [Docker](https://www.docker.com/) containers, but there are alternatives like [rkt](https://www.redhat.com/en/topics/containers/what-is-rkt) too.
- Any size application and dependencies can be containerized
- However, you should aspire towards composing a set of [_highly cohesive_](https://www.baeldung.com/cs/cohesion-vs-coupling) functionality into a single container.

Containerizing a service is simple and straightforward. 

1. The code, its dependencies, and runtime are packaged into a binary called a container image. 
2. Images are stored in a container registry, which acts as a repository or library for images. 
3. A registry can be located on your development computer, in your data center, or in a public cloud. 
4. Docker itself maintains a public registry via Docker Hub.

> While several container vendors exist, Docker has captured the lion's share of the market. The company has been driving the software container movement. It has become the de facto standard for packaging, deploying, and running cloud-native applications.

#### Why Containers?

- Containers provide portability and guarantee consistency across environments.
- By encapsulating everything into a single package, you isolate the service (that provides a set of cohesive functionality) and its dependencies _from the underlying infrastructure_.
- You can deploy the container in any environment that hosts the Docker runtime engine. Containerized workloads also eliminate the expense of pre-configuring each environment with frameworks, software libraries, and runtime engines.
- By sharing the underlying operating system and host resources, a container has a much smaller footprint than a full virtual machine. The smaller size increases the density, or number of services, that a given host can run at one time.

### Microservices

> Cloud-native systems embrace microservices, a popular architectural style for constructing modern applications.

The term _Microservices_ refers to an architectural approach based on multiple smaller, modular services. Each microservice has it's own codebase and is usually _owned and maintained_ by a separate [_small_](https://docs.aws.amazon.com/whitepapers/latest/introduction-devops-aws/two-pizza-teams.html) team.

A background in [Domain Driven Design](https://medium.com/ssense-tech/domain-driven-design-everything-you-always-wanted-to-know-about-it-but-were-afraid-to-ask-a85e7b74497a) is essential to structure microservices.

> Domain Driven Design: “A specific sphere of activity or knowledge that defines a set of common requirements, terminology, and functionality on which the application logic works to solve a problem.”

It focuses mainly on a business problem and how to strictly organize the logic that solves it. This approach was first described by Eric Evans in his book [Domain-Driven Design Tackling Complexity in the Heart of Software](https://www.goodreads.com/book/show/179133.Domain_Driven_Design).

#### Bounded Context

In Domain Driven Design, _Bounded Context_ is a way to break the domain into multiple cohesive wholes, each of which have their own unified model both in concept and in code.

For example, let us say you are building a software platform to offer Supply Chain Financing as a Service. Here _Supply Chain Financing_ is the domain. Some of the bounded contexts could be
- **Origination** - the process flow that on-boards a small business and provides them with a credit limit)
- **Financing** - the process flow that starts with a small business submitting an invoice & ends with the invoice being funded through credit limit consumption)
- **Rewards** - Gamified update of credit limits, based on the repayment behavior of the small business

You can structure each of the above sub-domains as a set of microservices, each providing a cohesive set of functionality.

#### Key Characteristics of Microservices

- Each implements a specific business capability within a larger domain context.
- Each is developed autonomously and can be deployed independently.
- Each is self-contained encapsulating its own data storage technology, dependencies, and programming platform.
- The services are not aware of other services that luve outside the _bounded context_.
- Each service can be deployed, updated, and scaled independently, thus making the overall architecture _Loosely coupled_.

> **When you embark on your journey to build your software application as a set of microservices, always start with the domain and discover bounded contexts within your domain. This allows you to build your application as a set of cohesive and loosely coupled services.** 


