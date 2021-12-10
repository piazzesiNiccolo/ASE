# Questions on the syllabus

**RESTful services**

1. How can we create/update/access resources in REST? Which are the pros and cons of REST?

   **In REST a resource is created/updated/accessed ecc. using HTTP methods. Clients invoke methods such as GET, POST, PUT, DELETE and request and responses  are used to trasnfer representaion of resources. Rest is resources centric and services are seen as reources identified by their URI. **

  **PROS:**

   - Simplicity
     - Low learning curve
       - Rest uses well known standards such as HTTP and the necessary infrastructure is already pervasive
     - Minimal tooling necessary to deploy services
       - Similar to building a dynamic web site
       - no custom client-side software
       - Can begin testing using a simple web browser
     - Because of URIs and hyperlinks we can discover web based resources without complusory registration to a repository
   - Efficiency  
     - lightweight protocols and message formats
   - Scalability
     - stateless RESTful web services can serve a very large amount of clients

​	  **CONS**:



  - Confusion on best practices( should i use POST OR PUT? What code should i return? What is the correct URI?)

  - No commonly accepted marshalling merchanism, so it's challenging to encored complex data structures in a URI
  - Not easy to extend restful services to support advanced functionalities in an interoperable manner
  - Very easy to make decisions on restful services that can cause significan technical risks and development effort(e.g design of the specification of resources and URI addressing scheme)

​					

​		

2. What is OpenAPI?

**Microservices**

3. Why microservices?

4. Which are the main characteristics, and the main pros and cons, of microservice-based architectures?

5. Which refactoring can be applied to resolve architectural smell X? How can we automate the generation of a model of a
microservice-based architecture?

6. What is Flask?

7. What is a container/image/volume in Docker? Wich are the differences between a virtual machine and a container?

8. What is the effect of docker build/run/commit? What is Docker Compose?

**Software testing**

9. What is development/release/user testing? What is TDD? What is partition testing? What are “software inspections”?

10. What is Locust?



**User stories**

11. What is a user story? Which are the six main attributes for a good user story?



**Business process modelling**

12. What is a parallel/exclusive/inclusive gateway in BPMN?

13. What is a workflow net? What is a sound workflow net? What is a live/bounded Petri net?

14. How can we model BPMN parallel/exclusive/inclusive gateways with workflow nets?

15. What is Camunda? Which are the two “usage patterns” of Camunda?



**Security and microservices**

16. Which are the main challenges in securing microservices? Which are the main “smells” in microservices security?

17. What is static/dynamic vulnerability analysis?

18. Which are the most frequent API security vulnerabilities?

19. What are authentication and authorization? What are SAML, OIDS and OAuth2.0?



**Splitting the monolith**

20. When and where to start splitting a monolith codebase? How to split databases?

21. What is the CAP theorem? What is the SAGA pattern?

22. What is a (event) data pump?

**Cloud-IoT continuum**

23. What is Fog computing? What are (declarative) application placement and continuous reasoning over the Cloud-IoT
continuum?

24. How can we assess the security level of an application deployment? How can we model trust?

25. What is secure FaaS orchestration?