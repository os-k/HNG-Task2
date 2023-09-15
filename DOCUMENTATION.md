# Simple REST API Documentation

This documentation provides an overview of the Simple REST API for managing a "person" resource. The API allows you to perform CRUD (Create, Read, Update, Delete) operations on person records.

## Table of Contents

1. [Setup Instructions](#setup-instructions)
2. [API Endpoints](#api-endpoints)
   - [Create a Person](#create-a-person)
   - [Fetch a Person](#fetch-a-person)
   - [Update a Person](#update-a-person)
   - [Delete a Person](#delete-a-person)
   - [Fetch by Name](#fetch-by-name)
3. [Sample Usage](#sample-usage)
4. [Validation](#validation)
5. [Known Limitations](#known-limitations)
6. [Local Deployment](#local-deployment)

## Setup Instructions

To set up and run the API locally, i followed these steps:

1. Clone the repository to my local machine.
2. Install the required dependencies using `pip install -r requirements.txt`.
3. Ran the API using `python RestApi.py`.
4. The API will be accessible at `http://localhost:5000`.

## API Endpoints

### Create a Person

- **URL:** `http://localhost:5000/api`
- **Method:** POST
- **Request Body:**
  ```json
  {
    "name": "John Doe"
  }

- **Request (Success):**

Status Code: 200 OK
- **Response Body:**
{
  "message": "Person created successfully"
}
- **Response (Error - Name Missing):**
Status Code: 400 Bad Request
Response Body:
{
  "error": "Name is required"
Fetch Details of a Person by ID
}
Request:

- **URL:**  `http://localhost:5000/api/1`
- **Method:** GET
- **Response (Success):**

Status Code: 200 OK
Response Body:
{
  "id": 1,
  "name": "John Doe"
}
- **Response (Error - Person Not Found):**
Status Code: 404 Not Found
Response Body:
{
  "message": "Person not found"
}

Update Details of an Existing Person
Request:

- **URL:**  `http://localhost:5000/api/1`
- **Method:** PUT
- **Request Body:**
{
  "name": "Jane Doe"
}

Response (Success):

Status Code: 200 OK
- **Response Body:**
{
  "message": "Person updated successfully"
}
- **Response (Error - Person Not Found):**

Status Code: 404 Not Found
- **Response Body:**
{
  "message": "Person not found"
}

Delete a Person
Request:

- **URL:**  `http://localhost:5000/api/1`
- **Method:** DELETE
- **Response (Success):**
Status Code: 200 OK

- **Response Body:**
{
  "message": "Person deleted successfully"
}

- **Response (Error - Person Not Found):**
Status Code: 404 Not Found
- **Response Body:**
{
  "message": "Person not found"
}

Fetch a Person by Name
Request:

- **URL:**  `http://localhost:5000/api/name/John%20Doe` 
- **Method:** GET
- **Response (Success):**
Status Code: 200 OK
- **Response Body:**
{
  "id": 1,
  "name": "John Doe"
}

Response (Error - Person Not Found):

Status Code: 404 Not Found
- **Response Body:**
{
  "message": "Person not found"
}
    
Validation
Fields are validated to accept only string values. Integers or other data types are not allowed.