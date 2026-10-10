# Whiteboard Project

A full-stack collaborative whiteboard application where users can create boards, draw in real time, and share canvases with other registered users. The project combines a React frontend with an Express + Socket.io backend and MongoDB persistence.

## Features

- User registration and login with JWT-based authentication
- Create, list, and delete multiple whiteboards
- Share a board with another user by email
- Real-time canvas updates using Socket.io
- Drawing tools for freehand brush, line, rectangle, circle, arrow, eraser, and text
- Undo and redo actions
- Download the board as a PNG image
- Persistent storage of canvases in MongoDB

## Tech Stack

- Frontend: React, React Router, Tailwind CSS, rough.js, perfect-freehand, socket.io-client
- Backend: Node.js, Express.js, MongoDB, Mongoose, JWT, socket.io
- Database: MongoDB

## Project Structure

```text
whiteboard_project/
├── backend/
│   ├── config/
│   ├── controllers/
│   ├── middlewares/
│   ├── models/
│   ├── routes/
│   ├── server.js
│   ├── package.json
│   └── package-lock.json
├── whiteboard-pro/
│   ├── public/
│   ├── src/
│   ├── package.json
│   ├── package-lock.json
│   ├── README.md
│   └── tailwind.config.js
├── .git/
└── README.md
```

## Getting Started

### 1) Install backend dependencies

```bash
cd backend
npm install
```

### 2) Start the backend server

```bash
npm start
```

The backend runs on port 5000 and provides REST APIs for user and canvas management, plus real-time socket events for collaborative drawing.

### 3) Install frontend dependencies

```bash
cd ../whiteboard-pro
npm install
```

### 4) Start the frontend app

```bash
npm start
```

The frontend development server starts with Create React App and is typically available at http://localhost:3000.

## Important Notes

- The frontend currently calls a hosted backend API URL in several places. If you are running the app locally, update those API URLs to your local backend server (for example, http://localhost:5000) before testing.
- MongoDB connection details are configured in the backend under `backend/config/db.js`.
- Authentication is required for creating, loading, sharing, and deleting canvases.

## Backend API Overview

- `POST /api/users/register` – Register a new user
- `POST /api/users/login` – Log in and receive a JWT token
- `POST /api/canvas/create` – Create a new canvas
- `GET /api/canvas/list` – Get canvases available to the user
- `GET /api/canvas/load/:id` – Load a specific canvas
- `PUT /api/canvas/share/:id` – Share a canvas with another user
- `DELETE /api/canvas/delete/:id` – Delete a canvas

## License

This project does not currently include a license file in the repository, so licensing terms are not explicitly defined here.
