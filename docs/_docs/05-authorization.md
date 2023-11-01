---
title: "Authorization"
permalink: /docs/authorization/
toc: false
---

[Graphql Authorization](https://github.com/graph-quilt/graphql-authorization-java) is a powerful way for securing a GraphQL service using attribute level access control.

### Overview

Graphql Authorization enforces access control on GraphQL queries by checking for allowed types and fields. A GraphQL query that has access to some of the requested fields/types will return:
* Requested fields it has access to
* Authorization Error message for the fields it does not have access to. You can customize the error message by over-riding the getErrorMessage method in the ScopeProvider interface.

With graphql authorization you can restrict access to subgraph for different user profiles:
   * Real user vs System user
   * Session with a lower access level 
   * User consented data access 
   * Intuit vs Third party apps

### Architecture

![architecture diagram](/docs/img/arch/graphql-authorization.png)

The authz-instrumentation will look at the fields in the request query, apply the authz rules and then redact them if needed before the query execution.

Schema Authoring:
* Client needs to creates request access to a particular part of super graph with query syntax & identification.
* PR is validated against the schema with plugins
* Subgraph owner approves the PR, and then its merged at which point it gets uploaded to s3.
* Orchestrator is listening to such authz events. On receiving such events, authz rules are updated without needing any service restarts.