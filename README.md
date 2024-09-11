# Backend YouTube Project


- [Thanks To chai-aur-code](https://youtu.be/EH3vGeqeIAo?feature=shared)


## Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Installation](#installation)
- [Running the Project](#running-the-project)
- [API Endpoints](#api-endpoints)
- [Future Improvements](#future-improvements)
- [License](#license)

## Overview
This project is a backend system for a YouTube-like application that supports user registration, login, and logout functionalities. As development progresses, more features like video uploading, comments, likes, and subscriptions are being added.

## Features
- **User Authentication:**
  - User registration (with email and password)
  - User login (JWT-based)
  - User logout (token invalidation)
  
- **Additional Features in Progress:**
  - Video management (upload, delete, and edit videos)
  - Like/dislike system for videos
  - Comment system
  - Subscription to other users
  - User profile management

## Technologies Used
- **Backend Framework:** Node.js with Express
- **Database:** MongoDB with Mongoose
- **Authentication:** JSON Web Token (JWT)
- **Message Broker (for future features):** RabbitMQ
- **File Storage:** (e.g., AWS S3, local storage, etc.)
- **Containerization:** Docker (for RabbitMQ and other services)

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/Ishaan1103/Backend-youtube
    cd Backend-youtube
    ```

2. **Install dependencies:**
    ```bash
    npm install
    ```

3. **Set up environment variables:**

    Create a `.env` file in the root of your project and add the following:
    ```bash
    PORT = 3000 //(depend upon u i used 3000)
    URI= Create One mongoDb server and use its uri here
    CORS_ORIGIN = *
    ACCESS_TOKEN_SECERET = Your ACCESS_TOKEN_SECERET 
    ACCESS_TOKEN_EXPIRY = Your ACCESS_TOKEN_EXPIRY
    REFRESH_TOKEN_SECERET = Your REFRESH_TOKEN_SECERET
    REFRESH_TOKEN_EXPIRY = Your REFRESH_TOKEN_EXPIRY(in numbers)
    CLOUD_NAME= Your-Cloud-name
    API_KEY= Your_Api_Key-from-Cloudinary 
    API_SECERET= Your_Api_Seceret-from-Cloudinary
    ```
   
4. **Start the server:**
    ```bash
    npm run dev
    ```

## Running the Project

Once you have completed the setup, you can run the project using:
```bash
npm start
```
This will start the server, and the application will be available on `http://localhost:3000`.

## API Endpoints

### Auth
| Method | Endpoint          | Description           | Protected |
|--------|-------------------|-----------------------|-----------|
| POST   | `/api/v1/auth/register` | Register a new user   | No        |
| POST   | `/api/v1/auth/login`    | Login and get token   | No        |
| POST   | `/api/v1/auth/logout`   | Logout user           | Yes       |

### Videos (in-progress)
| Method | Endpoint                | Description                       | Protected |
|--------|-------------------------|-----------------------------------|-----------|
| POST   | `/api/v1/videos/upload`     | Upload a video                    | Yes       |
| GET    | `/api/v1/videos/:id`        | Get a specific video by its ID    | No        |
| DELETE | `/api/v1/videos/:id`        | Delete a video by its ID          | Yes       |
| PUT    | `/api/v1/videos/:id`        | Update video details              | Yes       |

### Comments (in-progress)
| Method | Endpoint                 | Description                       | Protected |
|--------|--------------------------|-----------------------------------|-----------|
| POST   | `/api/v1/comments/:videoId`  | Post a comment on a video         | Yes       |
| GET    | `/api/v1/comments/:videoId`  | Get comments for a specific video | No        |

## Future Improvements
- **Video Recommendations:** Recommend videos based on user preferences.
- **Analytics:** Track views and other engagement metrics.
- **Notifications:** Real-time notifications for new comments, likes, and subscriptions.
- **Microservices Architecture:** Plan to scale the application by breaking features into microservices.
- **CI/CD:** Set up automated testing and deployment pipelines.
