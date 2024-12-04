# Node.js GraphQL MongoDB Project

This project demonstrates a basic Node.js application that uses GraphQL to interact with a MongoDB database. It allows users to create, update, retrieve, and delete user data.

---

## Features

- **GraphQL API**:

  - Add new users.
  - Retrieve a single user by ID.
  - Retrieve a list of all users.
  - Update user details.
  - Delete a user by ID.
- **MongoDB Integration**:

  - Models and schema are defined using Mongoose.
  - Connection string included for MongoDB Atlas.

---

## Prerequisites

Ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (v14 or higher recommended)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- MongoDB Atlas or a local MongoDB instance.

---

## Installation

1. Clone the repository:

   ```bash
   git clone https://dsudi1113/node-graphql-mongodb.git
   cd node-graphql-mongodb
   ```
2. Install dependencies:

   ```bash
   npm install
   ```
3. Set up your MongoDB connection string:

   In the app.js file, replace <db_user> , <db_password> and `<db-name>` in the connection string with your MongoDB connection string:

   ```javascript
   const uri = "mongodb+srv://<db_user>:<db_password>@cluster0.2jqlu.mongodb.net/<db-name>?retryWrites=true&w=majority&appName=Cluster0";
   ```
4. Start the server:

```bash
node app.js
```

## GraphQL API Endpoints

The API is accessible at:
`http://localhost:4000/graphql`

You can use GraphiQL or a similar GraphQL client to interact with the API.

---

### Example Queries and Mutations

#### Add a User

```graphql
mutation {
  addUser(name: "Alice", email: "alice@example.com", password: "securepassword123") {
    id
    name
    email
  }
}
```

#### Retrieve All Users

```graphql
query {
  users {
    id
    name
    email
  }
}
```

#### Update a User

```graphql
mutation {
  updateUser(id: "USER_ID_HERE", name: "Jane Doe", email: "jane@example.com") {
    id
    name
    email
  }
}

```

#### Delete a User

```graphql

mutation {
  deleteUser(id: "USER_ID_HERE") {
    id
    name
    email
  }
}


```

## Project Structure

```bash

node-graphql-mongodb/
├── app.js             # Entry point of the application
├── schema.js          # GraphQL schema and resolvers
├── package.json       # Project metadata and dependencies
├── README.md          # Documentation

```

### **Dependencies**

Node.js
Express.js
GraphQL
Mongoose
dotenv
Install dependencies via:

```bash
npm install
```

### Security Note

Do not store passwords in plain text. Use a hashing library like bcrypt to hash passwords before saving them to the database.
Store sensitive configuration values like the MongoDB connection string in a .env file.

### License

This project is licensed under the MIT License. See the LICENSE file for details.
