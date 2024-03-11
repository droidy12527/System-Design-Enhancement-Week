### Auth Service

- **Endpoint:** `/auth/login`
- **Method:** POST
- **Description:** Authenticates the user.
- **Request Body:** 
  ```json
  { "username": "example", "password": "example123" }

- **Response:** 
- `200 OK`: 
  ```
  { "success": true, "token": "<JWT_token>" }
  ```
- `401 Unauthorized`: 
  ```
  { "success": false, "message": "Invalid credentials" }
  ```

### Subscription Service

- **Endpoint:** `/subscription/check`
- **Method:** GET
- **Description:** Checks the user's subscription status.
- **Request Headers:** 
  ```json
  { "Authorization": "Bearer <JWT_token>" }
  - **Response:** 
- `200 OK`: 
  ```
  { "success": true, "subscription": "HD Plan" }
  ```
- `403 Forbidden`: 
  ```
  { "success": false, "message": "Subscription required" }
  ```

### Location Service

- **Endpoint:** `/location/map`
- **Method:** GET
- **Description:** Maps the video catalogue to the user's location.
- **Request Headers:** 
