# GraphQL vs REST

### GraphQL is a query language

<img src="../images/Back-end/RESTAPI_endpoint.png" width=800>
REST API which can lead to over fetching

<img src="../images/Back-end/graphql_vs_REST.png" width=800>
GraphQL only gets back the data fields we need.

# 1. Setup a server with Apollo server

https://www.apollographql.com/docs/apollo-server/getting-started/

```bash
npm init --yes && npm pkg set type="module"

npm install @apollo/server graphql
```

# 2. define schema & type

use schema to define the structure of data set that clients can query.

## scalar type

```js
String, Int, Float, Boolean, ID;
```

## Object type

```js
type Character {
  name: String!
  appearsIn: [Episode!]!
}
```

## query & mutation type

Every GraphQL service has a **query** type and may or may not have a **mutation** type. they are special object because they define the **entry point** of every GraphQL query.

```js
export const typeDefs = `#graphql
  type Game {
    id:ID!
    title:String!
    platform:[String!]!
  }
  type Review {
    id: ID!
    rating: Int!
    content: String!
  }
  type Author {
    id: ID!
    name: String!
    verified: Boolean!
  }

  type Query {
    Review:[Review]
    Game: [Game]
    Author:[Author]
  }
`;
```

# 3. define a resolver

instruct Apollo Server that it should use that data set when executing a query.

# 4. Query variables

```js
review(_, args) {
      return db.reviews.find((review) => review.id === args.id);
    },
```

# 5. related data
