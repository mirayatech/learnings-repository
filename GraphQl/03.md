# Core Concepts of GraphQL 🌐

Welcome to the "Core Concepts of GraphQL" section in my learning repository. Let's delve into the essential aspects that define GraphQL.

## Schema Definition Language (SDL)📜

```javascript
type User {
  id: ID!
  name: String!
  email: String!
}
```

- **❗️ means Non-Nullable**: When you see `ID!`, `String!`, or any type followed by an exclamation mark, it indicates that the field must always have a value and that it cannot be null.

### Types:

- string: text
- int: whole numbers
- float: decimal numbers
- boolean: true/false
- ID: key for data object

## Schema 🗺️

A GraphQL schema defines the capabilities of your API. It acts as a contract between the client and the server. In your schema:

```javascript
type Query {
  getUser(id: ID!): User
}

type Mutation {
  updateUser(id: ID!, name: String!): User
}
```

- **Root Types**: The schema includes three root types: `Query`, `Mutation`, and `Subscription`.
  - `Query` allows clients to retrieve data.
  - `Mutation` is for modifying data, such as updating a user's name.
  - `Subscription` enables real-time updates.

## Queries 📋

Queries are the way clients request data from your API. In your query:

```javascript
query {
  getUser(id: "abc123") {
    name
    email
  }
}
```

- **Queries**: Clients use queries to request specific data fields. In this example, we're requesting the `name` and `email` fields for a user.

### Fetching Data with Queries 🚀

GraphQL queries are like getting exactly what you want from a single endpoint, without having to ask multiple times. It's like grabbing just the right item you need from a store shelf.

## Mutation 🔄

Mutations change data in your API. When you perform a mutation, like creating or updating something, GraphQL often responds with a `payload.`

- **Payload:** It's like a message that tells you what was done. If you create a user, the payload might tell you the user's ID and name, confirming the action and showing what was modified. It's like a notification that lets you know what happened.

- **Create**:

```javascript
mutation {
  createUser(name: "John", age: 30) {
    id
    name
  }
}
```

- **Update**:

```javascript
mutation {
  updateUser(id: "abc123", name: "New Name") {
    id
    name
  }
}
```

- **Delete**:

```javascript
mutation {
  deleteUser(id: "xyz789") {
    id
  }
}
```

## Subscription 📡

Subscriptions bring real-time features to GraphQL. They let clients join in on special events and instantly get updates when those events happen. Subscriptions work great for things like chat apps, live notifications, and real-time dashboards.

## Example of Full Schema

```javascript
type Mutation {
  createUser(name: String!, age: Int!): User!
  createPost(title: String!, author: ID!): Post!
  deletePost(id: ID!): Boolean!
}

type Query {
  getUser(id: ID!): User!
  getPostsByUser(userId: ID!): [Post!]!
}

type Subscription {
  newPost: Post!
}

type User {
  id: ID!
  name: String!
  age: Int!
  posts: [Post!]!
}

type Post {
  id: ID!
  title: String!
  author: User!
}
```

- **Full Schema Example**: This schema defines types, mutations, queries, and subscriptions for a GraphQL API. The `User` type, has fields like `id`, `name`, `age`, and `posts`, showing relationships between types.
