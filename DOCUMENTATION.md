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
  ```json
  { "Authorization": "Bearer <JWT_token>" }
  - **Response:** 
- `200 OK`: 
  ```
  { "success": true, "location": "US" }
  ```
- `403 Forbidden`: 
  ```
  { "success": false, "message": "Location not authorized" }
  ```

### Video Transcoding Service

- **Endpoint:** `/video/transcode`
- **Method:** POST
- **Description:** Transcodes video into different formats.
- **Request Body:** 
  ```json
  { "video_url": "https://example.com/video.mp4", "bandwidth": "medium" }
  - **Response:** 
- `200 OK`: 
  ```
  { "success": true, "transcoded_url": "https://example.com/transcoded_video.mp4" }
  ```
- `400 Bad Request`: 
  ```
  { "success": false, "message": "Invalid video URL" }
  ```

### Notification Service

- **Endpoint:** `/notification/broadcast`
- **Method:** POST
- **Description:** Broadcasts notifications for newly uploaded videos.
- **Request Body:** 
  ```json
  { "video_id": "123456", "message": "New video uploaded" }
  - **Response:** 
- `200 OK`: 
  ```
  { "success": true, "message": "Notification broadcasted successfully" }
  ```
- `500 Internal Server Error`: 
  ```
  { "success": false, "message": "Error broadcasting notification" }
  ```

### Payment Service

- **Endpoint:** `/payment/authorize`
- **Method:** POST
- **Description:** Authorizes the payment using a third-party service like Stripe.
- **Request Body:** 
  ```json
  - **Response:** 
- `200 OK`: 
  ```
  { "success": true, "message": "Payment authorized successfully" }
  ```
- `402 Payment Required`: 
  ```
  { "success": false, "message": "Payment authorization failed" }
  ```

### User Profile Service

- **Endpoint:** `/user/profile`
- **Method:** GET
- **Description:** Retrieves the user's profile details.
- **Request Headers:** 
  ```json
  { "Authorization": "Bearer <JWT_token>" }
  - **Response:** 
- `200 OK`: 
  ```
  { "success": true, "profile": { "username": "example", "email": "example@example.com", "subscription": "HD Plan" } }
  ```
- `401 Unauthorized`: 
  ```
  { "success": false, "message": "Invalid token" }
  ```

### Video Upload Service

- **Endpoint:** `/video/upload`
- **Method:** POST
- **Description:** Allows internal teams to upload videos for transcription and distribution.
- **Request Body:** 
  ```json
  { "video_file": "<video_data>", "region": "US" 
  - **Response:** 
- `200 OK`: 
  ```
  { "success": true, "message": "Video uploaded successfully" }
  ```
- `500 Internal Server Error`: 
  ```
  { "success": false, "message": "Error uploading video" }
  ```



