# eShopOnContainers with CAP

This is a fork of a sample .NET Core reference application [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers) developed by Microsoft, modified to run on top of [CAP](https://github.com/dotnetcore/CAP). 

The application is based on a simplified microservices architecture and Docker containers. It is more comprehensive and complex than typical sample applications. In particular, it shows many CAP features working together.

**If you have any comments, please open an issue in this repository**


## eShopOnContainers Architecture overview 

This reference application is cross-platform at the server and client side, thanks to .NET Core services capable of running on Linux or Windows containers depending on your Docker host, and to Xamarin for mobile apps running on Android, iOS or Windows/UWP plus any browser for the client web apps.
The architecture proposes a microservice oriented architecture implementation with multiple autonomous microservices (each one owning its own data/db) and implementing different approaches within each microservice (simple CRUD vs. DDD/CQRS patterns) using Http as the communication protocol between the client apps and the microservices and supports asynchronous communication for data updates propagation across multiple services based on Integration Events and an Event Bus plus other features defined at the <a href='https://github.com/dotnet/eShopOnContainers/wiki/01.-Roadmap-and-Milestones-for-future-releases'>roadmap</a>.
<p>
<img src="https://user-images.githubusercontent.com/1712635/38758862-d4b42498-3f27-11e8-8dad-db60b0fa05d3.png">
<p>

## CAP overview

CAP is a library based on .Net standard, which is a solution to deal with distributed transactions, also has the function of EventBus, it is lightweight, easy to use, and efficiently.

Microsoft's eShopOnContainers solution contains a simple, light-weight IEventBus implementation running on top of RabbitMQ. That implementation is only intended for development and testing. In this fork we replaced the test implementation with NServiceBus.

CAP is adopted the local message table program integrated with the current database to solve the exception may occur in the process of the distributed system calling each other. It can ensure that the event messages are not lost in any case.

CAP provides a simpler way to implement event publishing and subscriptions, you do not need to inherit or implement any interface during the process of subscription and sending.

>CAP implements the Outbox Pattern described in the [eShop ebook](https://docs.microsoft.com/en-us/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/subscribe-events#designing-atomicity-and-resiliency-when-publishing-to-the-event-bus)
<img src="https://docs.microsoft.com/en-us/dotnet/standard/microservices-architecture/multi-container-microservice-net-applications/media/image24.png">


## Setting up your development environment for eShopOnContainers
### Visual Studio 2017 and Windows based
This is the more straightforward way to get started:
https://github.com/dotnet-architecture/eShopOnContainers/wiki/02.-Setting-eShopOnContainers-in-a-Visual-Studio-2017-environment

### CLI and Windows based
For those who prefer the CLI on Windows, using dotnet CLI, docker CLI and VS Code for Windows:
https://github.com/dotnet/eShopOnContainers/wiki/03.-Setting-the-eShopOnContainers-solution-up-in-a-Windows-CLI-environment-(dotnet-CLI,-Docker-CLI-and-VS-Code)

### CLI and Mac based
For those who prefer the CLI on a Mac, using dotnet CLI, docker CLI and VS Code for Mac:
https://github.com/dotnet-architecture/eShopOnContainers/wiki/04.-Setting-eShopOnContainer-solution-up-in-a-Mac,-VS-for-Mac-or-with-CLI-environment--(dotnet-CLI,-Docker-CLI-and-VS-Code)

## Orchestrators: Kubernetes and Service Fabric
See at the [Wiki](https://github.com/dotnet-architecture/eShopOnContainers/wiki) the posts on setup/instructions about how to deploy to Kubernetes or Service Fabric in Azure (although you could also deploy to any other cloud or on-premises).

## Sending feedback and pull requests
As mentioned, we'd appreciate your feedback, improvements and ideas.
You can create new issues at the issues section, do pull requests and/or send emails to **eshop_feedback@service.microsoft.com**

## Questions
[QUESTION] Answer +1 if the solution is working for you (Through VS2017 or CLI environment):
https://github.com/dotnet/eShopOnContainers/issues/107
