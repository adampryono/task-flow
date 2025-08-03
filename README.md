# Task Manager Application

A simple task management web application built with Vue.js 3 and Node.js.

## Features

- User Authentication (Login & Register)
- JWT-based authentication
- Create, Read, Update, Delete tasks
- Filter tasks by status (Todo, In Progress, Done)
- Search tasks by title
- Responsive design with Tailwind CSS

## Tech Stack

- **Frontend**: Vue.js 3 (Composition API), Vite, Tailwind CSS
- **Backend**: Node.js, Express.js
- **Database**: MySQL with Sequelize ORM
- **Authentication**: JWT

## Prerequisites

- Node.js (v14 or higher)
- MySQL Server
- npm or yarn

## Installation

1. Clone the repository

2. Install root dependencies:
   ```bash
   npm install
   ```

3. Install backend dependencies:
   ```bash
   cd backend
   npm install
   cd ..
   ```

4. Install frontend dependencies:
   ```bash
   cd frontend
   npm install
   cd ..
   ```

   Or use the all-in-one command (after fixing package.json):
   ```bash
   npm run install:all
   ```

5. Set up MySQL database and create a database named `task_manager`

6. Create `.env` file in the backend folder (see Environment Variables section)

7. Run database migrations:
   ```bash
   cd backend
   npx sequelize-cli db:migrate
   ```

8. Start development servers:
   ```bash
   npm run dev
   ```

The frontend will be available at `http://localhost:3000` and the backend at `http://localhost:5000`.

## Environment Variables

Create a `.env` file in the backend folder with:

```env
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=yourpassword
DB_NAME=task_manager
DB_PORT=3306
PORT=5000
JWT_SECRET=your-super-secret-jwt-key
JWT_EXPIRE=7d
NODE_ENV=development
```

## API Endpoints

- `POST /api/auth/register` - Register new user
- `POST /api/auth/login` - Login user
- `GET /api/tasks` - Get all tasks (authenticated)
- `POST /api/tasks` - Create new task (authenticated)
- `PUT /api/tasks/:id` - Update task (authenticated)
- `DELETE /api/tasks/:id` - Delete task (authenticated)

## Project Structure

```
task-manager/
├── backend/
│   ├── src/
│   │   ├── config/
│   │   ├── controllers/
│   │   ├── middleware/
│   │   ├── models/
│   │   ├── routes/
│   │   └── server.js
│   ├── .env
│   └── package.json
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── composables/
│   │   ├── router/
│   │   ├── views/
│   │   ├── App.vue
│   │   ├── main.js
│   │   └── style.css
│   ├── index.html
│   └── package.json
├── package.json
└── README.md
```

## Troubleshooting

### Database Connection Issues
- Ensure MySQL is running
- Check database credentials in `.env` file
- Make sure the database `task_manager` exists

### Installation Issues
- Clear npm cache: `npm cache clean --force`
- Delete `node_modules` folders and `package-lock.json` files, then reinstall

## Deployment

- Backend: Deploy to Railway, Render, or Heroku
- Frontend: Deploy to Netlify or Vercel

## Future Enhancements

- Drag and drop task reordering
- Task categories/labels
- Due date reminders
- Task sharing between users
- Dark mode support
