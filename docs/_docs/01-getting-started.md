---
title: "Getting Started"
permalink: /docs/getting-started/
toc: false
---

Graph Quilt comes with a GraphQL Gateway which was built using Spring Boot Webflux.  It exposes two end points:
1. /graphql - this is the endpoint that accepts GraphQL Requests.
2. /register - this is used by services to register their schema

AWS S3 is used as the service registry repository. When run locally, it uses localhost to mock S3.  

## Clone graphql-quilt-gateway

```
$ git clone https://github.com/graph-quilt/graph-quilt-gateway.git
```

## Run with Docket Compose

The docker compose will start both **localstack** and **graphql gateway**.  To start, run the command

`$ docker compose up`

You should see the Spring Boot Logo and a message "Started GraphQLGatewayApplication ..."
  
## Test using GraphiQL

Navigate to [http://localhost:7000/graphiql](http://localhost:7000/graphiql) 