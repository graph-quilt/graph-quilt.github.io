---
layout: home
---

Graph Quilt is an open architecture for creating a unified graph that aggregates and combines multiple 
GraphQL APIs.  The main component is the Graph Quilt Gateway which runs on Spring Boot Webflux.  Yes... it is **reactive**!

<img src="./assets/img/gateway-diagram.png"
     alt="Markdown Monster icon"
     style="float: left; margin-right: 10px;" />
  
Graph Quilt Gateway exposes data from multiple sources through a single GraphQL endpoint. It uses [nested 
stitching and federation](https://graphquilt.medium.com/graphql-orchestration-combining-schema-stitching-federation-2f5b9e2f70) to create the unified graph from dynamically registered sources.  It will split 
all incoming queries into multiple sub-queries, orchestrate these sub-queries to appropriate data providers 
and aggregate providers’ responses into a single response before returning it to the client.
