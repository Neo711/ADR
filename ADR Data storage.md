# Architectural Decision Record: Data Storage Solution

- **Status**: Proposed
- **Date**: 2023-10-10

## Context

Our university's social networking app is expected to handle a large amount of data, ranging from user profiles, class information, events, clubs, to announcements, assignments, and grades. Given the requirements of offline access, cross-platform support, and data security, choosing the right data storage solution is paramount.

## Decision

We have chosen to implement a combination of **Relational Database Management System (RDBMS)** for structured data and **NoSQL** for flexible data structures. Specifically, we'll use **PostgreSQL** for relational data and **MongoDB** for unstructured or flexible schema data.

## Rationale

### Pros:

- Scalability and flexibility in managing various types of data.
- Ensures data consistency and integrity for crucial data points.
- Both databases have strong communities, ensuring regular updates and patches.

- **RDBMS (PostgreSQL)**:
  - Well-suited for structured data like user profiles, class schedules, and grades.
  - Strong ACID (Atomicity, Consistency, Isolation, Durability) properties ensuring data integrity.
  - Rich querying capabilities, making it easier to retrieve and manipulate data.
  - Good support for integrating with Active Directory for user management.
  - Mature, robust, and has a strong community backing.

- **NoSQL (MongoDB)**:
  - Suitable for flexible or dynamic data structures, such as event or club data which may have varying attributes.
  - Scalable and can handle large volumes of data efficiently.
  - Enables fast writes, suitable for features like real-time posts or comments.

- **Offline Support**: Both databases support mechanisms to store data offline and synchronize when online. Integration with mobile app frameworks will further assist in this regard.

- **Security**: PostgreSQL and MongoDB both offer advanced security features, including encryption at rest and in transit, and can be configured to adhere to data protection regulations.

## Consequences

### Cons:

- Complexity in managing and syncing two different database systems.
- Requires expertise in both RDBMS and NoSQL paradigms.

### Risks:

- Misconfigurations can lead to data breaches or loss.
- Ensuring synchronized data integrity between two systems can be challenging.

## Next Steps

- Set up initial database schemas and structures for both PostgreSQL and MongoDB.
- Develop data access layers in the backend to interact with these databases.
- Ensure strict security protocols are followed during setup, including encryption and firewall configurations.

