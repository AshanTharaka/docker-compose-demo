\# Docker Compose Deployment — Maven Demo



This repository contains the Docker Compose configuration for running the Maven Demo Spring Boot application with PostgreSQL.



\## Architecture



\- \*\*Application:\*\* Spring Boot REST API

\- \*\*Container image:\*\* `ashanweerasekara/maven-demo:latest`

\- \*\*Database:\*\* PostgreSQL 16

\- \*\*Orchestration:\*\* Docker Compose

\- \*\*Persistent storage:\*\* Docker named volume



\## Prerequisites



\- Docker Desktop

\- Docker Compose

\- Internet connection to pull container images



\## Setup



1\. Clone this repository.

2\. Create a `.env` file in the project root:



```dotenv

POSTGRES\_DB=devshop

POSTGRES\_USER=devops

POSTGRES\_PASSWORD=replace\_with\_a\_strong\_password

```



3\. Start the services:



```bash

docker compose up -d --pull always

```



4\. Check service status:



```bash

docker compose ps

```



5\. Test the API:



```bash

curl http://localhost:8081/api/hello

curl http://localhost:8081/api/products

```



\## Stop the Services



```bash

docker compose down

```



The PostgreSQL data volume is retained when you stop the services this way.



To delete the database volume as well, use `docker compose down -v`. \*\*Warning:\*\* this deletes the persisted database data.



\## Security



\- The `.env` file is excluded from Git using `.gitignore`.

\- Never commit real database passwords or other secrets.

\- Replace the example password with a strong, private password before starting the services.



\## Related Repository



Spring Boot application source code and CI/CD pipeline:



https://github.com/AshanTharaka/maven-demo



