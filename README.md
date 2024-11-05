<p align="center">
  <a href="http://nestjs.com/" target="blank"><img src="https://nestjs.com/img/logo-small.svg" width="120" alt="Nest Logo" /></a>
</p>

[circleci-image]: https://img.shields.io/circleci/build/github/nestjs/nest/master?token=abc123def456
[circleci-url]: https://circleci.com/gh/nestjs/nest

  <p align="center"><b>LIB-NEST-API</b></p>

## Description

lib-nest-api is a backend api server build on [Nest](https://github.com/nestjs/nest) framework. Serving features like adding, updating, deleting books for the book library system.

## Project setup

```bash
$ npm install
```
## Create .env file
Create a new env file on the root level and add the following text.
```
DB_URI={YOUR MONGO URI}
```


## Compile and run the project

```bash
# development
$ npm run start

# watch mode
$ npm run start:dev

# production mode
$ npm run start:prod
```

## Run tests

```bash
# unit tests
$ npm run test

# e2e tests
$ npm run test:e2e

# test coverage
$ npm run test:cov
```

### Library App API Documentation

This is the API documentation for the Library App, a Nest.js application that provides endpoints for managing a collection of books.

## Table of Contents
- [Overview](#overview)
- [Base URL](#base-url)
- [Endpoints](#endpoints)
  - [Get All Books](#1-get-all-books)
  - [Create a Book](#2-create-a-book)
  - [Get a Book by ID](#3-get-a-book-by-id)
  - [Update a Book](#4-update-a-book)
  - [Delete a Book](#5-delete-a-book)
- [Data Transfer Objects (DTOs)](#data-transfer-objects-dtos)
  - [CreateBookDto](#createbookdto)
  - [UpdateBookDto](#updatebookdto)
- [Error Handling](#error-handling)
- [Conclusion](#conclusion)

## Overview
This API provides functionality for managing books in a library application built using Nest.js. Users can create, read, update, and delete books in the collection.

## Base URL
http://localhost:3000/books

## Endpoints

### 1. Get All Books
- **Endpoint:** `GET /books`
- **Description:** Retrieves a list of all books.
- **Response:**
  - **Status Code:** `200 OK`
  - **Body:**
    ```json
    [
      {
        "id": "string",
        "title": "string",
        "description": "string",
        "author": "string",
        "price": "number",
        "category": {
          "name": "string",
          "description": "string"
        }
      }
    ]
    ```

### 2. Create a Book
- **Endpoint:** `POST /books`
- **Description:** Creates a new book in the library.
- **Request Body:**
  - **Content-Type:** `application/json`
  - **Body:**
    ```json
    {
      "title": "string",
      "description": "string",
      "author": "string",
      "price": "number",
      "category": {
        "name": "string",
        "description": "string"
      }
    }
    ```
- **Response:**
  - **Status Code:** `201 Created`
  - **Body:**
    ```json
    {
      "id": "string",
      "title": "string",
      "description": "string",
      "author": "string",
      "price": "number",
      "category": {
        "name": "string",
        "description": "string"
      }
    }
    ```

### 3. Get a Book by ID
- **Endpoint:** `GET /books/:id`
- **Description:** Retrieves a book by its ID.
- **Parameters:**
  - `id` (string): The ID of the book to retrieve.
- **Response:**
  - **Status Code:** `200 OK`
  - **Body:**
    ```json
    {
      "id": "string",
      "title": "string",
      "description": "string",
      "author": "string",
      "price": "number",
      "category": {
        "name": "string",
        "description": "string"
      }
    }
    ```
- **Error Response:**
  - **Status Code:** `404 Not Found`
  - **Body:**
    ```json
    {
      "statusCode": 404,
      "message": "Book not found!"
    }
    ```

### 4. Update a Book
- **Endpoint:** `PUT /books/:id`
- **Description:** Updates an existing book by its ID.
- **Parameters:**
  - `id` (string): The ID of the book to update.
- **Request Body:**
  - **Content-Type:** `application/json`
  - **Body:**
    ```json
    {
      "title": "string",
      "description": "string",
      "author": "string",
      "price": "number",
      "category": {
        "name": "string",
        "description": "string"
      }
    }
    ```
- **Response:**
  - **Status Code:** `200 OK`
  - **Body:**
    ```json
    {
      "id": "string",
      "title": "string",
      "description": "string",
      "author": "string",
      "price": "number",
      "category": {
        "name": "string",
        "description": "string"
      }
    }
    ```

### 5. Delete a Book
- **Endpoint:** `DELETE /books/:id`
- **Description:** Deletes a book by its ID.
- **Parameters:**
  - `id` (string): The ID of the book to delete.
- **Response:**
  - **Status Code:** `200 OK`
  - **Body:**
    ```json
    {
      "id": "string",
      "title": "string",
      "description": "string",
      "author": "string",
      "price": "number",
      "category": {
        "name": "string",
        "description": "string"
      }
    }
    ```
- **Error Response:**
  - **Status Code:** `404 Not Found`
  - **Body:**
    ```json
    {
      "statusCode": 404,
      "message": "Book not found!"
    }
    ```

## Data Transfer Objects (DTOs)

### CreateBookDto
```typescript
export class CreateBookDto {
    readonly title: string;
    readonly description: string;
    readonly author: string;
    readonly price: number;
    readonly category: Category;
}
```

### UpdateBookDto
```typescript
export class UpdateBookDto {
    readonly title: string;
    readonly description: string;
    readonly author: string;
    readonly price: number;
    readonly category: Category;
}
```
### Error Handling
The API will return appropriate HTTP status codes and error messages for any failed operations. Common error responses include ```404 Not Found``` for non-existing resources.

### Conclusion
This API allows for full CRUD (Create, Read, Update, Delete) operations on books within the library application. Each endpoint is designed to handle specific requests, ensuring a clear and efficient interaction with the underlying database.

## Contributor
<b>[Anand Pothraj](https://anandpothraj.netlify.app/)</b>
