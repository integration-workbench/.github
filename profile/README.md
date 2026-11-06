# Integration Workbench

Integration Workbench is an independent Java 21 and Spring Boot project for managing contacts across Salesforce and HubSpot from a local workspace. It explores how to handle each CRM’s authentication and data format while giving the local application its own storage and editing rules.

## Services

| Service | What’s in place |
| --- | --- |
| **CRM Integration Service** | Reads contacts from Salesforce and HubSpot and exposes them in a common JSON format. Each contact retains its source and external ID. |
| **[Record Service](https://github.com/integration-workbench/record-service)** | Provides a REST API to create, read, update, and delete local contacts. It uses MySQL with Flyway migrations and JPA optimistic locking to reject stale edits. The repository includes Docker Compose setup and integration tests that run against MySQL with Testcontainers. |

The services run independently today. The next milestone is to import contacts from Salesforce and HubSpot and save them in Record Service’s MySQL database so they can be reviewed and edited locally. From there, the goal is to write local edits back to the CRMs and propagate changes made in either CRM so both stay in sync.

## Browse the code

Start with [Record Service](https://github.com/integration-workbench/record-service) for local setup, example API requests, and tests. The CRM Integration Service source is currently private. Browse all public projects in the [organization’s repository list](https://github.com/orgs/integration-workbench/repositories).
