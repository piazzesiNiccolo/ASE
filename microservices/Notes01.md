# MicroServices 

## Why microservies?
1. shorter lead time
	- faster redeploy

2. need to **scale** effectively
	- millions of users

## ~~Monolith~~
1. Typical enterprise application

2. Cons
	- slower rebuilding and redeploy

	- scaling of entire application, instead of single parts

# Essence of microservices

1. Service-orientation
	- Applications as sets of services
	- each runs in its own container
	- lightweight communication mechanims (Rest-like protocols)
		- Http communication, dumb message bus( synchronous or asynchronous when needed like rabbitMQ)
	- polyglotism (different technologies and languages

	~~ESBs~~ (*Smart endpoints, dumb pipes*)

> *The size of a microservice is the size of the team building it*

2. Organize services around business capabilities
	- agile development, cross functional teams, flat set of services managed by many teams
	
	- **Different teams with different roles introduces a delay of communications between teams.**

3. Decentralize data management
	- each service manage its own database
	- *eventual consinstency and compensations* instead of distributed transactions
    	- [ ] We accept some inconsisencies but sooner or later the data will be consistent again.
