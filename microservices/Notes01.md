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
	- lightweight communication mechanisms (Rest-like protocols)
		- Http communication, dumb message bus( synchronous or asynchronous when needed like rabbitMQ)
	- polyglotism (different technologies and languages) for different services

	~~ESBs (enterprise smart bus)~~ (*Smart endpoints, dumb pipes*)

> *The size of a microservice is the size of the team building it*

2. Organize services around business capabilities
	- agile development, cross functional teams, flat set of services managed by many teams
	
	- **Different teams with different roles introduces a delay of communications between teams.**

3. Decentralize data management
	
	- each service manage its own database
	
	- *eventual consinstency and compensations* instead of distributed transactions
        
		-  We accept some inconsisencies but sooner or later the data will be consistent again.

4. Independently deployed services
  
    - Each service should ideally start without any dependency on other services. Should reduce coupling as much as possible.


5. Horizontally scalable services
	
	- i replicate only services that needs to scale, not the entire application
    		
    	
		- need to be careful, if a service has end-point communication with  another service, horizontal scaling of the latter could not have the increase in perfomance that we want.


6. Fault resilient services

	- avoid cascading failures
	
	- **applications need to be designed so they can tolerate failure of services**
	
	- Any service call could fail for various reasons, client needs to address this as gracefully as possible (avoid starvation and crashes). 
	
	- Netflix API (2012)

		- billions of calls per day
		- several bilions outgoing calls to dozens of underlying subsystems 
		- across thousands of cloud instances
		- intermittent failure guaranteed with these many variables, even with excellent availability of each dependency

		> **Synchronous calls between services induce multiplicative effect of downtime**

  	### *Design for failure*

	
	### Test (bravely) &rarr; Chaos testing, fault injection

## DevOps
Development Operations

~~projects~~ products

> "You build it, you run it"

## Conclusions and remarks

- microservice architectural style is an important idea, worth serious consideration for enterprise applications
 
- Many pros
	- short lead time
	- effective scaling

- Cons
	- communication overhead
	- complexity
	- "wrong cuts", dependendt services (when changing *a* we also change *b*)
	- avoiding data duplication with isolated microservices can be massively complicated, need consistency checks at the application level.

- "A poor team will always create poor products"

> "Dont even consider microservices unless you have a system too complex to manage as a monolith"
