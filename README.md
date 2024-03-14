# Locale API Documentation

The Locale API provides endpoints for managing users, regions, states, local government areas (LGAs), user registration, user login, and user logout. It also supports API key generation and retrieval. This documentation outlines the API endpoints, request parameters, and response structures.

## Base URL
The base URL for accessing the API is `https://example.com`.

## Authentication
Authentication is required for certain endpoints using JWT (JSON Web Tokens). Users must sign up or sign in to obtain an access token.

## Endpoints

### Get Index
- **Description:** Retrieve the index message.
- **URL:** `/`
- **Method:** `GET`
- **Response:**
  ```json
  {
      "message": "Locale API!"
  }
  ```

### Get Users
- **Description:** Retrieve all users.
- **URL:** `/users`
- **Method:** `GET`
- **Response:** List of user objects:
  ```json
  [
      {
          "id": 1,
          "firstName": "John",
          "lastName": "Doe",
          "email": "john@example.com",
          "hashedPassword": "hashed_password"
      },
      ...
  ]
  ```

### Get User by ID
- **Description:** Retrieve a user by ID.
- **URL:** `/users/{id}`
- **Method:** `GET`
- **Path Parameters:**
  - `id` (integer): User ID
- **Response:** User object:
  ```json
  {
      "id": 1,
      "firstName": "John",
      "lastName": "Doe",
      "email": "john@example.com",
      "hashedPassword": "hashed_password"
  }
  ```

### Edit User Details
- **Description:** Edit user details by ID.
- **URL:** `/users/{id}`
- **Method:** `PUT`
- **Path Parameters:**
  - `id` (integer): User ID
- **Request Body:** User update object
- **Response:** Updated user object

### Generate API Key
- **Description:** Generate an API key for a user.
- **URL:** `/api-key/{apiKey}`
- **Method:** `POST`
- **Path Parameters:**
  - `apiKey` (string): API key
- **Response:** API key object
  ```json
  {
      "api_key": "generated_api_key"
  }
  ```

### Get API Key
- **Description:** Retrieve an API key for a user.
- **URL:** `/api-key/{apiKey}`
- **Method:** `GET`
- **Path Parameters:**
  - `apiKey` (string): API key
- **Response:** API key object
  ```json
  {
      "api_key": "user_api_key"
  }
  ```

### Get Regions
- **Description:** Retrieve all regions.
- **URL:** `/regions`
- **Method:** `GET`
- **Response:** List of region objects

### Get Region by ID
- **Description:** Retrieve a region by ID.
- **URL:** `/regions/{region_id}`
- **Method:** `GET`
- **Path Parameters:**
  - `region_id` (integer): Region ID
- **Response:** Region object

### Get States
- **Description:** Retrieve all states.
- **URL:** `/states`
- **Method:** `GET`
- **Response:** List of state objects

### Get State by ID
- **Description:** Retrieve a state by ID.
- **URL:** `/states/{state_id}`
- **Method:** `GET`
- **Path Parameters:**
  - `state_id` (integer): State ID
- **Response:** State object

### Get LGAs
- **Description:** Retrieve all LGAs.
- **URL:** `/lgas`
- **Method:** `GET`
- **Response:** List of LGA objects

### Get LGA by ID
- **Description:** Retrieve an LGA by ID.
- **URL:** `/lgas/{lga_id}`
- **Method:** `GET`
- **Path Parameters:**
  - `lga_id` (integer): LGA ID
- **Response:** LGA object

### User Registration
- **Description:** Register a new user.
- **URL:** `/sign-up`
- **Method:** `POST`
- **Request Body:** User registration request object
- **Response:** User registration response object

### User Login
- **Description:** Authenticate a user and obtain an access token.
- **URL:** `/sign-in`
- **Method:** `POST`
- **Request Body:** User login request object
- **Response:** User login response object

### User Logout
- **Description:** Logout a user.
- **URL:** `/signout`
- **Method:** `POST`
- **Response:** Logout message

## Data Models
- **User Object:**
  - `id` (integer):

 User ID
  - `firstName` (string): User's first name
  - `lastName` (string): User's last name
  - `email` (string): User's email address
  - `hashedPassword` (string): Hashed user password
  - `api_key` (string): User's API key (optional)
  
- **Region Object:**
  - `region_id` (integer): Region ID
  - `name` (string): Region name
  
- **State Object:**
  - `state_id` (integer): State ID
  - `name` (string): State name
  
- **LGA Object:**
  - `lga_id` (integer): LGA ID
  - `name` (string): LGA name

## Error Responses
- **400 Bad Request:** Invalid request parameters or missing fields
- **401 Unauthorized:** User authentication failed
- **404 Not Found:** Resource not found

## Dependencies
- **Database URI:** `DATABASE_URI`
- **Secret Key:** `SECRET_KEY`
- **Google Maps API Key:** `GOOGLE_MAPS_API_KEY`

## Author
- Developed by Kehinde Ogundipe
  
## License
- This project is licensed under the MIT License.
