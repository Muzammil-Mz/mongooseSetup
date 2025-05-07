# mongooseSetup
Step by step mongo db setup and theory
DATABSASE:

A database is a structured collection of data that can be accessed, managed and updated efficiently.
Databases are essentiall for storing and managing data in applications, websites and business systems.

Types of Databases:

1. Relational Databases(RDBMS): (Table- rows and columns)

- Data is organized into tables (rows and columns)
- Uses SQL (structured Query Language) for queries
- Examples: MySQL, PostgreSQL, Oracle, SQL Server

2. NoSQL Databases:

- Types:

1. Document Based: MongoDB, CouchDB
2. Key value stores: Redis, DynamoDB
3. Column-Family stores: Cassandra, HBase
4. Graph Databases: Neo4j

3. NewSQL Databases:

- Combines relational models with NoSQL scalability.
- Examples: CockroachDB, Google Spanner.

Popular Databases in the Market:

1. Relational Databases (SQL-Based):

- PostgreSQL: Open sournce, advanced RDBMS with robust features like ACID compliance, complex queries and scalability
-MySQL: Widely used open source RDBMS, popular in web apps.
-SQLite: Lightweight and embedded RDBMS for smaller apps.

2. NoSQL Databases:

-MongoDB: A document oriented NoSQL database, ideal for unstructured data
-Cassandra: High availability and fault tolerance for massive datasets
- Redis: In-memory key-value store for caching and real time apps

3. NewSQL and Modern Databases:

-CockroachDB: SQL-based, highly scalable, distributed database.
-Prisma (ORM tool): Not a database but a modern ORM for managing PostgreSQL, MySQL and other dbs

MongoDB:

It is a NoSQL document-oriented database that stores data in flexible, JSON like documents.
It's designed for scalability, high performance and ease of dev

-Features:

1. Document-oriented: Data is stored in BSON format (Binary JSON)
2. Schema-Less: Documents can have different structures
3. Scalability: Horizontal scaling through sharding
4. Indexing: Supports indexing for faster query execution
5. Aggregation Framework: Enables complex data analysis
6. High availability: Replica sets provide data redundancy

-Core conepts:
1. Database: A container for collections
2. Collection: A group of documents, similar to tables in SQL
3. Document: A set of key value pairs similar to rows in SQL
4. Fields: Key-value pairs in documents, like columns in SQL

Mongoose Overview:

Mongoose is an ODM (Object Data Modeling) library for MongoDB and Node.js. It provides a schema based solution to model application data, ensuring structure and validation. 

Mongoose Core concepts:

1. Schema: Defines the structure of document
2. Model: A class with which we create and query Documents
3. Document: An instance of a model, representing a MongoDB document

MongoDB setup:

1. Visit mongodb.com ; create an account and login
2. Select M0 cluster
3. type your name in lowercase and google cloud as provider
4. click on create deployment
5. Enter same  username and password (saad) while creating account
6. Choose connection method
7. We will be using compass - GUI tool for MongoDB
8. Choose Windows 64bit 10+ 
9. copy the link mongodb+srv://saad:saad@saad.jvsbc.mongodb.net/ (i got new link tho bc i created another cluster)
10. click Done.

MongoDB structure:

1. Organisations
2. Projects
3. Clusters
4. Database
5. Collection
6. Document (Object)
mongodb+srv://saad:<db_password>@saad.fww30.mongodb.net/

MongoDB shell commands:

1. use dbName - creates a database ; or switches into an existing one

2. db.createCollection("collectionName") - creates a collection in database **db is fixed here!!!*

3. db.collectionName.insertOne({"name":"Saad","age":20}) - adds a document in the collection 
- this is if were adding them one by one
- this is preffered.

4. db.collectionName.insertMany([{"name":"Rahman","age":20},{"name":"Ismail","age":22}])

5. db.collectionName.find({key: value}).pretty() - finds and desplays a user by the key given.

6. db.Users.updateOne(
  {id: "P01"},
  {
    $set: {name: "Saad Hussain", phoneNumber: "+919030358367"}
  }
  )

  what if i want to delete a specific key?
  instead of set we use "unset" and value ku empty string

  db.Users.updateOne(
  {id: "P01"},
  {
    $unset: {name: ""}
  }
  )

  deletes the name key 

  Updates the name and phoneNumber of a user with id: "PO1"
  i can create a new key like email simply by adding email: "blah@exmaple.com" in the $set line

  7. db.Users.deleteOne({id: "PO1"})
  deletes the user with id PO1

  8. db.collectionName.drop() - drops/deletes the collection

  9. db.dropDatabase() - deletes the entire database
