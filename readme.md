![Caju](https://raw.githubusercontent.com/ivanpaulovich/manga/master/docs/manga-icon.png) Caju: Back-end with awesome architectures made easy!
=========
Service Template to help you build evolvable and maintainable applications. It follows the principles from the [Clean Architecture book](https://www.amazon.com/Clean-Architecture-Craftsmans-Software-Structure/dp/0134494164) and built on Domain-Driven Design. This tool increases productivity on developing your next microservices.

![dotnet new caju](https://raw.githubusercontent.com/ivanpaulovich/caju/master/images/dotnet-new-caju.gif)

## Generate your own awesome Back-end!

To create a dotnet application based on this template:

```sh
dotnet new -i Paulovich.Caju
dotnet new caju -n "MyProject"
```

## The Architecture Styles

This architecture implementations is a software that encapsulate Business Rules in Use Cases and the Enteprise Rules in Entities. We prevent our software to be coupled from technology details like User Interface, Data Access frameworks or Web Servers. And there is some concepts which guided us:

| Concept | Description |
| --- | --- |
| DDD | This Bounded Context of this project contains the Ubiquitious Language around Account Balance and designed inside Domain Layer and Application layer. We use the Eric Evans terms like Entities, Value Object, Aggregates Root and Domain Events. |
| SOLID | The SOLID principles are all over the the solution. 
| Entity-Boundary-Interactor (EBI) | The software implementation is agnostic from technology, framework, or database. The result is focus on the  use cases with input/output ports. |
| Microservice | Designed around the Business Domain, having Continous Delivery and Independent Deployment. |

## Sample applications

Run `dotnet new -i Paulovich.Caju` then try the following commands.

Clean Architecture Solution with basic use cases:

```sh
dotnet new caju \
	--architecture-style clean \
	--use-cases basic \
	-n "Clean-BasicProject"
```

Hexagonal Architecture Solution with all use cases:

```sh
dotnet new caju \
	--architecture-style hexagonal \
	--use-cases full \
	-n "Hexagonal-FullProject"
```

Empty Event-Sourcing Solution:

```sh
dotnet new caju \
	--architecture-style eventsourcing \
	--use-cases empty \
	-n "EventSourcing-EmptyProject"
```

For olher solution types check out the [Caju Samples folder](https://github.com/ivanpaulovich/caju/tree/master/samples).

## Switches

There are switches to generate your awesome application with your needs. Try after `dotnet new caju`:

| Switch | Options | Default Value |
| --- | --- | --- |
| --architecture-style | `clean` `hexagonal` `eventsourcing` | `clean` |
| --use-cases | `full` `basic` `readonly` `none` | `full` |
| --ui | `both` `webapi` `console` `none` | `webapi` |
| --data-access | `mongo` `entityframework` `dapper` `none` | `mongo` |
| --tips | `true` `false` | `true` |
| --service-bus | `kafka` `none` | `kafka` |
> type `dotnet new caju --help` for the complete list of switches.

## Roadmap
<a href="https://www.nuget.org/packages/Paulovich.Caju/" rel="Paulovich.Caju">![NuGet](https://buildstats.info/nuget/paulovich.caju)</a> [![Build Status](https://travis-ci.org/ivanpaulovich/caju.svg?branch=master)](https://travis-ci.org/ivanpaulovich/caju)

* Allow to choose the **architecture style**
  * [Clean Architecture](https://github.com/ivanpaulovich/manga) :white_check_mark:
  * [Hexagonal Architecture](https://github.com/ivanpaulovich/acerola) :white_check_mark:
  * [Event-Sourcing](https://github.com/ivanpaulovich/castanha) :white_check_mark:
* Allow to choose built-in **use cases sets**
  * Full set of use cases :white_check_mark:
  * Basic set of use cases :white_check_mark:
  * Read Only :white_check_mark: 
  * None :white_check_mark:	
* Allow to choose **data access** frameworks 
  * MongoDB :white_check_mark:
  * Dapper
  * Entity Framework
  * Azure Cosmos DB
  * None :white_check_mark:
* Allow to choose **UI** frameworks
  * Both
  * WebAPI :white_check_mark:
  * Console 
  * None :white_check_mark:
* Allow to choose **Service Bus** frameworks
  * Kafka
  * Azure Event Bus
  * None
* Allow to skip the **dotnet restore** after code generation :white_check_mark:
* Allow to include or to remove the **architecture tips** :white_check_mark:

## Common Issues

Check your [.NET Core SDK](https://www.microsoft.com/net/download/windows). Our features are only supported in `2.1.4` SDK or plus.

```sh
$ dotnet --version
2.1.4
```
