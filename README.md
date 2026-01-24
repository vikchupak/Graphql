# About Graphql

Graphql (Apollo) Server sits between real frontend and backend?

Yes — that’s exactly the idea.

Think of **Apollo Server** as a **middleware layer** between your **frontend** (React, mobile apps, etc.) and your **backend systems** (databases, REST APIs, microservices, or other GraphQL services).

### 🏗 How it sits in the stack

```
Frontend (React, iOS, Android, Web) 
           ↓   (GraphQL queries)
     Apollo Server (GraphQL API)
           ↓   (resolvers, data sources)
Backend systems (REST APIs, DBs, microservices)
```

### 🔑 What it does in the middle

* **Receives GraphQL queries/mutations** from clients.
* **Parses & validates** them against the schema you define.
* **Executes resolvers**, which fetch data from your actual backend (DB, REST API, gRPC, etc.).
* **Returns a shaped JSON response** exactly matching what the frontend requested.

### ✨ Why this is useful

* **Frontend flexibility:** The frontend asks for *only the data it needs*, no over-fetching/under-fetching.
* **Single endpoint:** Clients don’t need to know about multiple microservices or databases — they just talk to Apollo Server.
* **Schema as contract:** Strongly typed schema ensures frontend and backend stay in sync.
* **Extensible:** You can add caching, logging, federation, authentication, and more at this layer.

---

👉 So yes: Apollo Server is a **bridge between frontend and backend**, exposing a clean GraphQL API while hiding the complexity of your underlying systems.

# Parallels with REST

- Graphql has 2 real "REST" endpoints
  - GET "/graphql" => GraphQL Playground (includes docs, schemas)
  - POST "/graphql" => query processing
- Graphql "query/mutation" - **WHAT** (like REST endpoint)
  - Query => like REST GET endpoint
  - Mutation => like REST POST/PUT/PATCH/DELETE endpoint
- Graphql "resolver" - **HOW** (like REST controller)
- Graphql "subscription" => like REST Web Sockets

Graphql
```txt
query -> POST /graphql endpoint -> resolver -> service -> repository -> model
```

REST
```txt
request -> endpoint -> controller -> service -> repository -> model
```
