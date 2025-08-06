# Task Management API

This Task Management API allows users to manage tasks effectively. It supports operations such as creating, reading, updating, and deleting tasks. The API is built with Node.js, Express.js, and Sequelize for MySQL database management, and includes JWT authentication for secure access.

## Features

- **CRUD Operations**: Create, Read, Update, and Delete tasks.
- **Task Properties**: Each task has a title, description, due date, status, and priority.
- **Task Status**: Tasks can have one of three statuses - Pending, In Progress, or Completed.
- **Task Priority**: Tasks can be marked with a priority of Low, Medium, or High.
- **User Authentication**: Users can register and log in to access the API securely using JWT tokens.

## Prerequisites

- Node.js (v14.x or higher)
- MySQL Database
- Postman (for testing the API)

## Setup and Installation

1. **Clone the Repository**

   ```bash
   git clone https://github.com/aniket-thapa/task-management-api.git
   cd task-management-api
   ```

2. **Install Dependencies**

   ```bash
   npm install
   ```

3. **Configure the Environment**
   Create a `.env` file in the root of the project with the following content:

   ```plaintext
   DB_HOST="localhost"
   DB_USER="root"
   DB_PASSWORD="yourpassword"
   DB_NAME="task_management_db"
   JWT_SECRET="your_jwt_secret_key"
   PORT=5000
   ```

4. **Setup the Database**
   Ensure your MySQL server is running. Then, create a database:

   ```sql
   CREATE DATABASE task_management_db;
   ```

5. **Sync the Database and Start the Server**
   This will sync your models with the database and start the server:

   ```bash
   node app.js
   ```

6. **Accessing the API**
   The API is accessible at `http://localhost:3000/api/tasks` for task management and `http://localhost:3000/api/auth` for authentication.

## API Endpoints and Testing the API with Postman:

### Authentication Endpoints

1. **Register a User**

- **URL**: `http://localhost:3000/api/auth/register`
- **Method**: `POST`
- **Request Body**: Go to the Body tab, select raw, and set the type to JSON. Add below JSON object and edit.

  ```json
  {
    "email": "your_email",
    "name": "your_name",
    "password": "your_password"
  }
  ```

- **Response**: Returns a success message upon registration.

2. **Login a User**

- **URL**: `http://localhost:3000/api/auth/login`
- **Method**: `POST`
- **Request Body**: Go to the Body tab, select raw, and set the type to JSON. Add below JSON object and edit.
  ```json
  {
    "email": "your_email",
    "password": "your_password"
  }
  ```
- **Response**: Returns a JWT token upon successful login.

### Task Management Endpoints (Protected)

1. **Create a Task**

- **URL**: `http://localhost:3000/api/tasks`
- **Method**: `POST`
- **Headers**: Include `Authorization: Bearer <token>` in the headers.
- **Request Body**:
  ```json
  {
    "title": "Task Title",
    "description": "Task Description",
    "dueDate": "2024-08-20",
    "status": "Pending",
    "priority": "Medium"
  }
  ```
- **Response**: Returns the created task.

2. **Get All Tasks**

- **URL**: `http://localhost:3000/api/tasks`
- **Method**: `GET`
- **Headers**: Include `Authorization: Bearer <token>` in the headers.
- **Response**: Returns a list of all tasks.

3. **Get a Single Task**

- **URL**: `http://localhost:3000/api/tasks/:id` (replace :id with the actual task ID).
- **Method**: `GET`
- **Headers**: Include `Authorization: Bearer <token>` in the headers.
- **Response**: Returns a single task by its ID.

4. **Update a Task**

- **URL**: `http://localhost:3000/api/tasks/:id` (replace :id with the actual task ID).
- **Method**: `PUT`
- **Headers**: Include `Authorization: Bearer <token>` in the headers.
- **Request Body**: Similar to create task with updated data.
- **Response**: Returns the updated task.

5. **Delete a Task**

- **URL**: `http://localhost:3000/api/tasks/:id` (replace :id with the actual task ID).
- **Method**: `DELETE`
- **Headers**: Include `Authorization: Bearer <token>` in the headers.
- **Response**: Returns a success message upon deletion.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Contact

For any questions or inquiries, feel free to reach out:

- **Email:** [mayankmayank1225@gmail.com](mailto:mayankmayank1225@gmail.com)
- **GitHub:** [github.com/mayank-verma04](https://github.com/mayank-verma04)
- **LinkedIn:** [linkedin.com/in/mayank-verma04](https://www.linkedin.com/in/mayank-verma04/)
