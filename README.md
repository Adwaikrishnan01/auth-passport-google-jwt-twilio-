
# Authentication using passport and phone number verification using Twilio

This project demonstrates the implementation of user authentication using Passport.js with JWT and Google OAuth strategies. It includes user registration, login, and access to protected routes. Users can verify phone number through sms by OTP.

## Table of Contents

- [Installation](#installation)
- [Configuration](#configuration)
- [Usage](#usage)
- [Endpoints](#endpoints)
- [Technologies](#technologies)
- [License](#license)

## Installation

1. Clone the repository:
   ```sh
   git clone https://github.com/Adwaikrishnan01/auth-passport-google-jwt-twilio-.git
   cd your-repo

2. Install dependencies:    
   ```sh
   npm install

3. Ensure you have MongoDB running on your local machine or provide a remote MongoDB URI.




## Configuration

1. Create a .env file in the root directory of the project and add the following environment variables:

    ```sh  
    GOOGLE_CLIENT_ID=your_google_client_id
    GOOGLE_CLIENT_SECRET=your_google_client_secret
    JWT_SECRET=your_jwt_secret
    SESSION_SECRET=your_session_secret
    MONGODB_URI=your_mongodb_uri
    TWILIO_VERIFY_SERVICE_SID=your_twilio_service_id
    TWILIO_AUTH_TOKEN=your_twilio_auth_token
    TWILIO_ACCOUNT_SID=your_twilio_account_SID
  
2. Adjust the passport-config.js file and other configuration files if necessary to match your environment and requirements.
## Usage 
 1. Start the server:

    ```sh
    npm run dev
 2. Open your browser and navigate to:
      ```sh
      http://localhost:3000

## Endpoints
# Authentication Endpoints
- **GET /auth/google:** Initiates Google OAuth authentication.
- **GET /auth/google/callback:** Handles the callback from Google OAuth.
- **POST /register:** Registers a new user with name, email, password, and phone.
- **POST /login:** Authenticates a user and returns a JWT token.
- **POST /verify:** Verifies the OTP sent to the user's phone number.

# Protected Routes
- **GET /protected-route-google:** A protected route accessible only after Google OAuth login.

# Twilio Integration
Twilio is used to send SMS-based OTP (One-Time Password) for Two-Factor Authentication (2FA). Below are the steps and example code for integrating Twilio with your project.

## Sending OTP
- When a user logs in, an OTP is sent to their registered phone number.



## Example request
# User Registration
    
    POST /signup
    Content-Type: application/json

    {
        "name": "John Doe",
        "email": "john@example.com",
        "password": "password123",
        "phone": "1234567890",
        "phone_verified: false
    }

# Login
        POST /login
        Content-Type: application/json

        {
            "email": "john@example.com",
            "password": "password123"
        }

# Verify phone

        POST /verify
        Content-Type: application/json

        {
            "phone": "1234567890"
            "OTP": "recieved OTP"
        }



# Technologies
- **Node.js:** JavaScript runtime environment
- **Express.js:** Web framework for Node.js
- **Passport.js:** Authentication middleware for Node.js
- **JWT:** JSON Web Tokens for authentication
- **Google OAuth 2.0:** For Google login
- **MongoDB:** NoSQL database
- **Mongoose:** ODM for MongoDB
- **EJS:** Embedded JavaScript templating
- **dotenv:** Environment variable management
- **Twilio:** For sending SMS-based OTPs
