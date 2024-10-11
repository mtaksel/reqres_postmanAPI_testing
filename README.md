Reqres API Postman Collection

This project contains a Postman collection that interacts with the Reqres API, a simple RESTful service providing a wide range of responses for testing purposes. The collection includes various endpoints to demonstrate basic CRUD operations, including user creation, retrieval, updating, and deletion, as well as user registration and login functionalities.

This Postman collection contains the following requests:

    ListUsers: Retrieves a paginated list of users.
    ListSingleUser: Retrieves the details of a specific user by their ID.
    CreateToken: Authenticates a user and generates a token.
    Create: Creates a new user with specified details.
    UpdatePut: Updates a user's information using the PUT method.
    UpdatePatch: Updates a user's information using the PATCH method.
    Delete: Deletes a user by their ID.
    Register - successful: Registers a user successfully.
    Register - unsuccessful: Attempts to register a user unsuccessfully (e.g., missing fields).

Project Structure

The structure of the collection is organized as follows:

    Requests: Each request is categorized based on the operation it performs (e.g., ListUsers, Create, Update, Delete).
    Test Scripts: Each request includes test scripts to validate the API response. These scripts check for status codes, response time, and the structure of the response data.
    Variables: The collection uses environment variables like authToken and id to store dynamic values such as authentication tokens and user IDs.

Example Requests & Responses
List Users

Request: GET https://reqres.in/api/users?page=2

Response:
```
json

{
    "page": 2,
    "per_page": 6,
    "total": 12,
    "total_pages": 2,
    "data": [
        {
            "id": 7,
            "email": "michael.lawson@reqres.in",
            "first_name": "Michael",
            "last_name": "Lawson",
            "avatar": "https://s3.amazonaws.com/uifaces/faces/twitter/follettkyle/128.jpg"
        },
    ]
}
```
Create a New User

Request: POST https://reqres.in/api/users

Request Body:
```
json

{
    "name": "morpheus",
    "job": "leader"
}
```
Response:
```
json

{
    "name": "morpheus",
    "job": "leader",
    "id": "123",
    "createdAt": "2023-08-11T12:00:00.000Z"
}
```
How to Use

    Import the Collection: Download the collection file and import it into Postman.
    Set Up Environment: Create an environment in Postman and define necessary variables like authToken and id.
    Execute Requests: Run the requests individually or in a sequence using Postman’s Collection Runner.
    View Test Results: Check the results of the test scripts in the "Tests" tab of each request.

Test Scripts

Each request includes automated test scripts that check:

    Status Code Validation: Ensures the API returns the expected status code.
    Response Time: Verifies the response time is within acceptable limits.
    Response Data Structure: Confirms that the response data contains the expected properties.

Environment Variables

    authToken: Used to store the authentication token retrieved from the CreateToken request.
    id: Used to store the ID of the user created or retrieved during the requests.
