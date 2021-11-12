

# Security and microservices

## Challenges

The broader the attack surface, the higher the risk

Monolith: inter-component communications within single process

Microservices:

- inter-service communications via remote calls

- large number of entry points, **attack surface broadens**

- security of app: strength of weakest link

  [image]

## Distributed security screening

Monolit: security screening done once, request dispatched to corresponding component

Each microservice has to carry out independent security screening

- May need to connect to a remote security token service
- repeated, distributed security checks affect latency and performance

Work around: trust the network:

Industry trend: from trust the networl to zero trust networking principles

Still overall performance must be taken into consideration

## Bootstrapping trust among microservices

Service-to-service communication must take place on protected channels

Suppose that you use certificates:

- Each microservice must be provisioned with a certificate ( and corresponding private key) to authenticate itself to another microservice during service-to-service interactions
- Recipient microservice must know how to validate the certificate associated with calling microservice
- Need a way to **bootstrap** trust between microservices
- (need also to revoke and rotate certificates)

&rarr; To manage large scale deployments of hundreds of microservices, **automation** is needed

## Tracing requests spanning multiple microservices

A log is the recording of an even of a service

A set of logs can be aggregate to produce *metrics* that reflects the system state (e.g. average invalid access requests per hour) and that may trigger alerts



*Traces* help you track a request from the point where it enters the system to the point where it leaves the system

**Correlating requests among microservices is challenging**

Tools

- e.g Prometheus and Grafana to monitor incoming requests
- e.g. Jaeger and Zipkin for distributed tracing



## Container complicate credentials/policies handling

Containers are immutable servers, they don't change state after spinup

​	Great to simplify deployment and to achieve horizontal-scalability

But for each service we need to maintain a dynamic list of allowed clients and a dynamic set of access-control policies

​	e.g get updated policies from some policy admin endpoint(push vs pull model)

Each service must maintain its own credentials, which need to be rotated periodically

 	e.g keep credentials in container filesystem and inject them at boot time



## Distribution makes sharing user context harder

User context has to be passed explicitly from one microservice to another

Challenge: Build trust between microservices so that receiving microservice accepts user context passed from calling microservice

Popular solution: Using JSON Web Token(JWT) to share user context among microservices

​	Idea: messages carrying user context in cryptographically safe way

## Decentralized security responsibilities

Polyglot architecture: Different squads can use different technology stacks

Different teams can use different security best practices, and different tools for static code analysis and dynamic testing

Security responsibilites distributed across different teams

Orgs often adopt hybrid approach, with centralized security team and security experts in the teams
