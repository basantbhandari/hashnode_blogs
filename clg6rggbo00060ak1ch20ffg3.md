---
title: "What is GraphQL schema?"
datePublished: Fri Apr 07 2023 16:27:57 GMT+0000 (Coordinated Universal Time)
cuid: clg6rggbo00060ak1ch20ffg3
slug: what-is-graphql-schema
tags: graphql

---

GraphQL schema is a blueprint or contract that defines the types of data that can be queried or mutated in a GraphQL API. It defines the structure of the data available to clients and how clients can interact with that data.

A GraphQL schema consists of types, fields, and directives. Types are the building blocks of a schema, and they define the shape of data that can be returned in a query or mutation. Fields represent individual pieces of data within a type, and directives provide additional metadata to the schema.

The schema is typically defined using the GraphQL Schema Definition Language (SDL), which is a simple syntax for describing the types, fields, and directives of a schema. Once the schema is defined, it can be used by clients to query or mutate data in the API, and by servers to validate incoming requests and return the appropriate data.

Overall, the GraphQL schema is a critical component of any GraphQL API, as it defines the types of data available to clients and helps to ensure consistency and predictability in the API's behavior.

here's an example of a simple GraphQL schema:

```graphql
type Query {
  book(id: ID!): Book
  author(id: ID!): Author
}

type Book {
  id: ID!
  title: String!
  author: Author!
}

type Author {
  id: ID!
  name: String!
  books: [Book!]!
}
```

In this example, we have three types defined: `Query`, `Book`, and `Author`. The `Query` type is a special type that represents the entry point to the schema and defines the available queries.

The `Book` type represents a book and has three fields: `id`, `title`, and `author`. The `Author` type represents an author and has three fields: `id`, `name`, and `books`.

The `books` field on the `Author` type returns an array of `Book` objects, and the `author` field on the `Book` type returns an `Author` object. This creates a bi-directional relationship between the `Book` and `Author` types.

Clients can use this schema to query for a specific book or author by ID, and retrieve their associated data. For example, a client might send the following query to retrieve the name of the author of a specific book:

```graphql
query {
  book(id: "123") {
    title
    author {
      name
    }
  }
}
```

The server would then use the schema to validate the query and return the requested data.