# PyroRecon

A foundational application research and bug bounty framework.

## Features

- Subdomain enumeration
- Live host detection
- Port scanning (nmap, masscan)
- Technology detection
- Content discovery
- JavaScript analysis
- Vulnerability scanning (Nuclei, Nikto, SQLMap)
- OWASP ZAP integration
- Interactive visualization
- GraphQL API

## Prerequisites

- [Docker](https://docs.docker.com/get-docker/) (v20.10+)
- [Docker Compose](https://docs.docker.com/compose/install/) (v2.0+)
- Minimum 8GB RAM recommended
- 20GB+ free disk space

## Quick Start

1. **Clone this repository**
   ```bash
   git clone https://github.com/papv2/pyrorecon.git
   cd pyrorecon
   ```


2. **Start the platform**
    ```
    docker compose up -d
    ```
    

## Wait for services to start (first run may take a few minutes)

    ```
    docker compose logs -f
    ```

## Access the application
    Frontend: http://localhost
    Backend API: http://localhost:8000
    GraphQL Playground: http://localhost:8000/graphql
    Services
    Service	Port	Description
    Frontend	80	Web UI
    Backend	8000	API Server
    PostgreSQL	5432	Database
    Neo4j	7474, 7687	Graph Database
    ZAP	8080	OWASP ZAP Proxy


## Usage
Open http://localhost in your browser
Create a new workspace
Add target domains to your scope
Run subdomain enumeration
Detect live hosts
Run scans (ports, tech detection, content discovery)
Analyze findings in the dashboard

## Stopping the Platform
    ```
    docker compose down
    ```

## To remove all data (fresh start):
    ```
    docker compose down -v
    ```

## Updating
    ```
    docker compose pull
    docker compose up -d
    ```

## Troubleshooting
    Services not starting

# Check service status
    ```
    docker compose ps
    ```

# View logs
    ```
    docker compose logs backend
    docker compose logs frontend
    ```

## Database connection issues
    Wait for the health checks to pass. The backend waits for PostgreSQL, Redis, Neo4j, and ZAP to be healthy before starting.
    Out of memory
    Increase Docker's memory allocation to at least 8GB in Docker Desktop settings.

License
    MIT
