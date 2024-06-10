# ToDo App Backend

This is the backend API for a ToDo application. It allows users to register, log in, create, edit, delete, and view their to-do items.

## Features

- User registration and authentication
- Create, edit, delete, and view to-do items
- JWT authentication for securing endpoints

## Technology Stack

- Python
- Django
- Django REST Framework

## Installation

1. Clone the repository:

    ```sh
    git clone https://github.com/yourusername/todo-app-backend.git
    cd todo-app-backend
    ```

2. Create and activate a virtual environment:

    ```sh
    python -m venv venv
    .\venv\Scripts\activate  # On Windows
    source venv/bin/activate  # On macOS/Linux
    ```

3. Install the dependencies:

    ```sh
    pip install -r requirements.txt
    ```

4. Apply migrations:

    ```sh
    python manage.py migrate
    ```

5. Start the development server:

    ```sh
    python manage.py runserver
    ```

The backend API will be available at `http://127.0.0.1:8000/`.

## API Endpoints

### User Authentication

- **Register a new user**

    ```
    POST /api/user/register/
    ```

    **Request body:**
    ```json
    {
        "username": "yourusername",
        "password": "yourpassword"
    }
    ```

- **Login**

    ```
    POST /api/login/
    ```

    **Request body:**
    ```json
    {
        "username": "yourusername",
        "password": "yourpassword"
    }
    ```

- **Logout**

    ```
    POST /api/logout/
    ```

    **Headers:**
    ```
    Authorization: Bearer <your-token>
    ```

### ToDo Management

- **Get all todos**

    ```
    GET /api/todos/
    ```

    **Headers:**
    ```
    Authorization: Bearer <your-token>
    ```

- **Create a new todo**

    ```
    POST /api/todos/
    ```

    **Headers:**
    ```
    Authorization: Bearer <your-token>
    ```

    **Request body:**
    ```json
    {
        "title": "Your Todo Title",
        "description": "Your Todo Description"
    }
    ```

- **Edit a todo**

    ```
    PUT /api/todos/{id}/
    ```

    **Headers:**
    ```
    Authorization: Bearer <your-token>
    ```

    **Request body:**
    ```json
    {
        "title": "Updated Todo Title",
        "description": "Updated Todo Description"
    }
    ```

- **Delete a todo**

    ```
    DELETE /api/todos/{id}/
    ```

    **Headers:**
    ```
    Authorization: Bearer <your-token>
    ```

## Running Tests

To run the tests, use the following command:

```sh
python manage.py test
