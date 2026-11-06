# Integration Workbench

Integration Workbench is an independent Java 21 and Spring Boot project for bringing contacts from Salesforce and HubSpot into a local workspace. It explores how to handle each CRM’s authentication and data format while giving the local application its own storage and editing rules.

## Services

| Service | What’s in place |
| --- | --- |
| **CRM Integration Service** | Reads contacts from Salesforce and HubSpot and exposes them in a common JSON format. Each contact retains its source and external ID. |
| **Record Service** | Provides a REST API to create, read, update, and delete local contacts. It uses MySQL with Flyway migrations and JPA optimistic locking to reject stale edits. The repository includes Docker Compose setup and integration tests that run against MySQL with Testcontainers. |

The services run independently today. The next milestone is to connect CRM retrieval to local storage so imported contacts can be reviewed and edited in one place.

## Browse the code

Both service repositories are currently private. Public releases of the source will appear in the [organization’s repository list](https://github.com/orgs/integration-workbench/repositories).
