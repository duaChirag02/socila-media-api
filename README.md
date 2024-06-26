# socila-media-api


Social Media API
This is a social media API for managing users, posts, and interactions between users.

Setup Instructions
Clone Repository:

bash
Copy code
git clone <repository_url>
Alternatively, download and extract the zip file containing the code.

Install Dependencies:

bash
Copy code
cd social-media-api
npm install
Set Environment Variables:
Create a .env file in the root directory and add the following environment variables:

makefile
Copy code
PORT=3000
MONGODB_URI=mongodb://localhost:27017/social-media-db
JWT_SECRET=your_secret_key
Start the Server:

sql
Copy code
npm start
Access Instructions
The API will be accessible at http://localhost:3000/api.
Testing Instructions
User Registration:

Endpoint: POST /api/register
Payload:
json
Copy code
{
  "username": "example_user",
  "email": "example@example.com",
  "password": "password123"
}
User Login:

Endpoint: POST /api/login
Payload:
json
Copy code
{
  "email": "example@example.com",
  "password": "password123"
}
Create a Post:

Endpoint: POST /api/posts
Payload:
json
Copy code
{
  "title": "Sample Title",
  "content": "Sample Content"
}
Follow a User:

Endpoint: POST /api/users/:userId/follow
Payload:
json
Copy code
{
  "userId": "user_id_to_follow"
}
Unfollow a User:

Endpoint: DELETE /api/users/:userId/unfollow
Payload:
json
Copy code
{
  "userId": "user_id_to_unfollow"
}
Retrieve Followed Users' Posts:

Endpoint: GET /api/posts/followed
No payload required.
GraphQL Query for User Profile:

Endpoint: POST /graphql
Payload:
graphql
Copy code
query {
  user(id: "user_id") {
    username
    email
    // Additional fields you want to retrieve
  }
}
GraphQL Query for User Posts:

Endpoint: POST /graphql
Payload:
graphql
Copy code
query {
  userPosts(userId: "user_id") {
    id
    content
    createdAt
    // Additional fields you want to retrieve
  }
}
Additional Information
This API is built using Node.js, Express.js, MongoDB, and GraphQL.