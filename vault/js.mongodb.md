---
id: pxwgagboimf8m1chtypt111
title: MongoDB
desc: ''
updated: 1687802915637
created: 1662316275086
---
## MongoDB

- is distributed document database
- NoSQL
- uses json-like documents with optional schemas

## MongoDB Structure

- cluster
  - database
    - collection (SQL: table)
      - documents (SQL: records)

## Model

- model - schema
- Mongoose generates collections in mongodb
  - _id - unique id for each document

## Mongoose

Mongoose is [elegant MongoDB object modeling for Node.js](https://mongoosejs.com/)

- ODM (Object Data Modeling) library for MongoDB
- helps with data modeling, schema enforcement, model validation, and general data manipulation.

## Connection String
From mongo:   
`mongodb+srv://<uname>:<password>@...mongodb.net/<dbName>?retryWrites=true&w=majority`

`DB_STRING = mongodb+srv://tarat:tarat123@cluster0.b5awpho.mongodb.net/forHealth?retryWrites=true&w=majority`