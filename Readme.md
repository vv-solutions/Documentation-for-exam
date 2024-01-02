# MTOGO


## Domain Driven Design
When designing MTOGO we chose to use Domain Driven Design. Which is used to break down a domain into sub-domains and model the system accordingly. The goal of this being an application consisting of several services that each represent a business goal.

Domain Driven Design
The first part of Domain Driven Design is to work out the different subdomains which in the end make up the system. We did this together as a team, as everyone needs to agree on the subdomains and the language used to describe them. In the end we ended with 10 subdomains.

![subdomains.png](images%2Fsubdomains.png)


This process proved to be iterative, as new sub-domains kept coming up, as well as subdomains that were split into several, as they would be too large, and handle multiple business goals.
An example of this could be the part of the system handling everything supplier related. Where it started being one subdomain that handled all the suppliers, their products, and their kitchens. We then figured that splitting that subdomain into three subdomains would make more sense, as they each represent a separate business goal, being: Handling of suppliers, which includes supplier registration and management. Products which handle all the products that the suppliers offer, this includes uploading menus, and calculating prices of products including VAT. And lastly the kitchen subdomain which handles accepting, doing, and denying tickets.

The next step in the process was to find the key parts of each of the ten subdomains. This means that we identified what each of the subdomains required to work. This part of the process was also an iterative process.

![bounded-context.png](images%2Fbounded-context.png)


When figuring out what parts belong in which subdomain, we quickly found out that “order” would be a part of a lot of the subdomains. But because each subdomain has its own bounded context, where the language used may differ from each other, we could use other terms that more accurately describe a given part in each context. Which enables greater understanding of what the part actually is. By doing this, the “order” part which came up in a lot of systems, ended up being a ticket in the kitchen subdomain, a delivery in the delivery sub domain, and just an order, in the order taking subdomain.

Once we identified the subdomains, we could then make a context mapping, to gain an understanding of how the different subdomains would communicate with each other.

![context-mapping.png](images%2Fcontext-mapping.png)

The figure above is a simplified version of the complete context mapping, for the purpose of the report, we don’t show the connections between rating, notification, and metrics subdomain, so that it doesn’t get too cluttered.  Doing a context mapping proved to be a valuable tool, as it sparked a great conversation on how the subdomains need to communicate, for the system to work.


## Microservice Architecture 
We have chosen the microservice architecture. 

Domain driven design and microservice architecture go hand in hand. As all the identified subdomains can be mapped to microservices. At the time of writing, we have developed several proof-of-concept microservices from the subdomains. A visualization of how the subdomains are mapped to microservices can be seen in the level 2 C4 diagram below.  N.b. Each of the microservices has its own database, which is not shown in the diagram.

![level-2-c4.png](images%2Flevel-2-c4.png)


