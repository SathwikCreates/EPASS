1. Clone the Repository
bash
Copy code
git clone https://github.com/yourusername/leave-request-system.git
cd leave-request-system
2. Install Dependencies
Run the following command to install the required Node.js modules:

bash
Copy code
npm install
3. Start the Server
Run the following command to start the server:

bash
Copy code
node server.js
The server will start on http://localhost:3000. Open this URL in your browser to interact with the system.

How It Works
Sign Up: Users can sign up by providing their name, email, password, and role (either student or teacher).
Login: After signing up, users can log in using their email and password.
Leave Requests:
Students: Once logged in, students can submit leave requests specifying the reason and date.
Teachers: Teachers can view all pending leave requests and decide whether to approve or reject them.
API Endpoints
1. POST /signup
Description: Sign up a new user (student or teacher).
Request Body:
json
Copy code
{
  "name": "John Doe",
  "email": "john.doe@example.com",
  "password": "password123",
  "role": "student"
}
Response:
Success: 200 OK
Failure: 400 Bad Request (if user already exists)
2. POST /login
Description: Log in an existing user.
Request Body:
json
Copy code
{
  "email": "john.doe@example.com",
  "password": "password123"
}
Response:
Success: 200 OK with user data
Failure: 400 Bad Request (if invalid credentials)
3. POST /leave-request
Description: Submit a leave request for a student.
Request Body:
json
Copy code
{
  "userId": 1,
  "reason": "Sick Leave",
  "date": "2024-12-12"
}
Response:
Success: 200 OK
Failure: 400 Bad Request (if any field is missing)
Frontend Interaction
Sign-Up Form: The student or teacher provides their name, email, password, and role to sign up.
Login Form: Users log in with their email and password.
Student Dashboard: After logging in, students can fill out a leave request form with a reason and date.
Teacher Dashboard: Teachers can see a list of pending leave requests and take action (approve/decline).
Additional Notes
This project uses in-memory data for simplicity. You can replace it with a real database like SQLite or MongoDB to persist user and leave request data.
The login system is basic and does not include security measures like password hashing. You can enhance this by using libraries like bcrypt for password hashing and JWT (JSON Web Tokens) for authentication.
To Improve
Implement a real database (SQLite or MongoDB) for storing user and leave request data.
Add password hashing for secure password storage.
Implement JWT authentication for maintaining user sessions.
Add leave request management for teachers (view, approve/decline).
Improve error handling and validation for API requests.