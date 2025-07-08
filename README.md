📌 Project Description
This is a simple banking microservices application designed to demonstrate advanced architectural patterns such as CQRS (Command Query Responsibility Segregation) and Event Sourcing, implemented using the Axon Framework and Axon Server. It serves as a foundational example of how to structure scalable, loosely coupled services using Spring Cloud technologies.

🧱 Microservices Overview
The system is composed of the following core services:

Customer Service

Account Service

Loan Service

Card Service

Each service is independently built and follows a strict CQRS + Event Sourcing model:

Commands handle write operations and emit domain-specific events (e.g., CreateCardEvent, UpdateCardEvent, DeleteCardEvent).

Events are stored in Axon Server as the single source of truth.

Projections (Query Models) are built from these events and stored in query-side databases for efficient read operations.

🚀 Technologies Used
Spring Boot for each microservice

Spring Cloud Gateway for API Gateway and API Composition

Eureka Server for service discovery

Axon Framework & Axon Server for implementing CQRS and Event Sourcing

Spring Web & Spring Data for REST APIs and persistence layers (on query side)

🧠 Architecture Highlights
CQRS + ES: Commands and queries are completely separated to improve scalability and maintainability.

Event-Driven Communication: Services publish and react to events, reducing tight coupling.

API Composition: Spring Cloud Gateway provides aggregate endpoints that combine data from multiple services, enabling clients to retrieve unified views.

🔍 Example Use Case (Card Service)
A CreateCardCommand triggers a CardCreatedEvent, which is stored in Axon Server.

The CardCreatedEvent is projected into a query-side model and stored in a separate read database.

The query-side model is then used to handle GetCardByIdQuery efficiently.

