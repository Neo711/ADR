# Architectural Decision Record: Selection of Backend Language

- **Status**: Proposed
- **Date**: 2023-10-10

## Context

We are in the process of developing a comprehensive social networking app for a university, aiming to serve a diverse set of users, including students and professors. Several criteria, such as cross-platform capability, offline synchronization, security, push notifications, and accessibility, are driving the need for a robust backend. The choice of backend language is crucial in achieving these goals while ensuring scalability and maintainability.

## Decision

After extensive evaluation of various languages and frameworks, we have decided to use **Node.js** with the **Express.js** framework for our backend development.

## Rationale

### Pros:

- Fast development cycle due to JavaScript's widespread familiarity.
- Strong community support ensures quick solutions to potential issues.
- Availability of numerous packages and tools to accelerate development.

- **Scalability**: Node.js is known for its non-blocking I/O and event-driven architecture, making it suitable for handling concurrent requests, a possible scenario given the university's size.

- **Cross-platform**: Node.js is platform-agnostic, ensuring consistent behavior across different server operating systems.

- **Rich Ecosystem**: The npm registry provides a vast array of libraries and middleware, which can aid in implementing features like offline support, data synchronization, and push notifications.

- **Integration with Active Directory**: There are established npm packages like `passport-azure-ad` that can aid in integrating with Active Directory for authentication and authorization.

- **Performance**: Node.js can be optimized for performance and can work efficiently even under substantial loads, ensuring that the app remains responsive.

- **Security**: With the right packages and best practices, Node.js can offer secure endpoints, encryption, and compliance with data protection regulations.

- **Community Support**: A vast community backs Node.js, ensuring regular updates, patches, and solutions to common problems.

## Consequences

### Cons:

- Being single-threaded, CPU-intensive operations can block the Node.js event loop, affecting performance.
- Requires careful handling and structuring to ensure maintainability as the codebase grows.

### Risks:

- Dependency on third-party packages might introduce vulnerabilities if not vetted properly.
- Requires the team to keep up with the frequently updated ecosystem to ensure the use of latest best practices.

## Next Steps

- Set up a basic Node.js and Express.js server infrastructure.
- Begin integrating with the Active Directory for authentication.
- Prototype essential endpoints to serve initial app functionalities.

