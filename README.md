
# Notes App

A full-stack web application that allows users to create, manage and organize their notes with secure authentication.

## Project Description

Notes App is a modern web application built with React and Django that provides users with a simple and intuitive interface to manage their personal notes. The application features secure user authentication, real-time updates, and a responsive design.

## Features

- User authentication (login/signup)
- Create new notes with title and content
- View all personal notes
- Delete existing notes
- Secure JWT-based authentication
- Responsive design for mobile and desktop
- Protected routes for authenticated users

## Prerequisites & Dependencies

### Backend
- Python 3.x
- Django 4.2+
- Django REST Framework
- PostgreSQL
- django-cors-headers
- djangorestframework-simplejwt
- python-dotenv
- psycopg2-binary

### Frontend
- Node.js
- React 18.2+
- react-router-dom
- axios
- jwt-decode
- Vite

## Installation & Setup

1. Clone the repository:
```bash
git clone <repository-url>
cd notebook_app_marscode
```

2. Backend Setup:
```bash
cd backend
python -m venv venv
source venv/bin/activate  # On Unix/macOS
# or
.\venv\Scripts\activate  # On Windows
pip install -r requirements.txt
```

3. Create a `.env` file in the backend directory:
```
DB_NAME=your_db_name
DB_USER=your_db_user
DB_PWD=your_db_password
DB_HOST=your_db_host
DB_PORT=your_db_port
```

4. Run migrations:
```bash
python manage.py migrate
```

5. Frontend Setup:
```bash
cd ../frontend
npm install
```

## Running the Application

1. Start the backend server:
```bash
cd backend
python manage.py runserver
```
The backend will run on `http://localhost:8000`

2. Start the frontend development server:
```bash
cd frontend
npm run dev
```
The frontend will run on `http://localhost:5173`

## API Documentation

### Authentication Endpoints
- `POST /api/user/` - Register new user
- `POST /api/token/` - Login and obtain JWT tokens
- `POST /api/token/refresh/` - Refresh JWT token
- `POST /api/user/logout/` - Logout user

### Notes Management Endpoints
- `GET /api/notes/` - Get all notes for authenticated user
- `POST /api/notes/` - Create a new note
  ```json
  {
    "title": "Note Title",
    "content": "Note Content"
  }
  ```
- `DELETE /api/notes/{id}/` - Delete a specific note
- `PUT /api/notes/{id}/` - Update a specific note
  ```json
  {
    "title": "Updated Title",
    "content": "Updated Content"
  }
  ```

All notes endpoints require authentication with a valid JWT token:
```
Authorization: Bearer <your_jwt_token>
```

## Technologies Used

### Backend
- Django & Django REST Framework
- PostgreSQL database
- Simple JWT for authentication
- Python-dotenv for environment variables

### Frontend
- React with Vite
- React Router for navigation
- Axios for API requests
- JWT Decode for token handling
- CSS for styling

The application follows a RESTful architecture with a clear separation between frontend and backend services.
```