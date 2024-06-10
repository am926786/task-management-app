# Task Management Application

## Project Description
A full-stack task management application that allows users to create, update, delete, and filter tasks by status. The application is built using React for the front-end, Node.js with Express for the back-end, and MySQL for the database.


## Setup Instructions

### Database Setup
1. Open MySQL and run the following commands to set up the database:

   ```sql
   CREATE DATABASE task_management;

   USE task_management;

   CREATE TABLE tasks (
       id INT AUTO_INCREMENT PRIMARY KEY,
       title VARCHAR(255) NOT NULL,
       description TEXT,
       status ENUM('To Do', 'In Progress', 'Done') DEFAULT 'To Do',
       created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
       updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
   );
   
# Backend Setup
Navigate to the server directory and install the dependencies:

cd server
npm install
Update db.js with your MySQL credentials:

# server/db.js

const { Sequelize } = require('sequelize');

const sequelize = new Sequelize('task_management', 'your_mysql_username', 'your_mysql_password', {
  host: 'localhost',
  dialect: 'mysql'
});

module.exports = sequelize;
# Start the backend server:

node server.js
Frontend Setup
# Navigate to the client directory and install the dependencies:

cd client
npm install

# Start the frontend development server:

npm start

# Running the Application
Ensure the MySQL database is running and the task_management database has been set up.
Start the backend server by navigating to the server directory and running node server.js.
Start the frontend development server by navigating to the client directory and running npm start.
The application should be accessible at http://localhost:3000.

API Endpoints
GET /api/tasks
Fetch all tasks.

POST /api/tasks
Create a new task.

Request Body:
json
Copy code
{
  "title": "Task Title",
  "description": "Task Description",
  "status": "To Do"
}
PUT /api/tasks/
Update an existing task.

Request Body:
json
Copy code
{
  "title": "Updated Task Title",
  "description": "Updated Task Description",
  "status": "In Progress"
}
DELETE /api/tasks/
Delete a task by ID.

Frontend Components
TaskForm
Component to create or update a task.

TaskList
Component to display the list of tasks.

Filter
Component to filter tasks by status.

How to Run Tests
Frontend Tests
# Navigate to the client directory and run:

npm test
# Backend Tests
Ensure you have a testing framework like Jest installed.
Write your tests in the tests directory.
Run the tests using the testing framework.
Assumptions and Decisions
Tasks must have a title (mandatory field).
The status of a task can be 'To Do', 'In Progress', or 'Done'.
Additional optional features can be implemented to enhance the application.
# Bonus Features
The application can be extended with the following optional features:

User authentication and authorization to restrict access to tasks.
Task due dates and reminders.
Task sorting and searching capabilities.
User profiles with avatars.
# Conclusion
This Task Management Application provides a full-stack
