# Zoo Management System (Console Application)
Console-based backend application for managing animals and inventory in a zoo.
The project focuses on domain modeling, SOLID principles, and dependency injection
using Spring DI container. Includes unit tests and clear separation of business logic.
## Features
- Adding animals with mandatory health check via veterinary clinic
- Inventory management (animals are also inventory items)
- Calculation of total daily food consumption
- List of animals allowed for contact zoo
- Console-based menu for interaction
- ## Architecture Overview
The application is built around a clean domain model with clear separation of responsibilities.

Core components:
- `Animal` and subclasses – domain models for animals
- `IVetClinic` / `VetClinic` – animal health check abstraction
- `IInventory` / `Thing` – inventory abstraction
- `Zoo` – core domain service
- `AppConfig` – Spring DI configuration
- `Main` – console entry point
## SOLID Principles
- **Single Responsibility** – domain services and models have clearly defined responsibilities
- **Open/Closed** – new animal types can be added without modifying existing logic
- **Liskov Substitution** – all animal subclasses are interchangeable via base type
- **Interface Segregation** – separate interfaces for life-related and inventory-related behavior
- **Dependency Inversion** – high-level modules depend on abstractions, not implementations
## Dependency Injection
Spring is used as a DI container to decouple object creation from business logic.
Dependencies are configured in `AppConfig` using Java-based configuration.
## Testing
The project includes unit tests with coverage above 60%.
Tests focus on core business logic and domain behavior.
## CI

The project uses GitHub Actions for continuous integration.
Each push and pull request triggers a build and runs unit tests using Java 21 and Maven Wrapper.

## How to Run
Requirements:
- Java 21

Build & Run:
./mvnw clean package
./mvnw exec:java -Dexec.mainClass="org.example.app.Main"

Run tests:

./mvnw test

The project uses Maven Wrapper, so a local Maven installation is not required.
