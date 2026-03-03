# Skill Scape - Student Portfolio Platform

A full-stack web application built with Django (backend) and React (frontend) that connects students with recruiters through portfolio sharing.

## Features

### For Students
- Create and manage personal portfolios
- Showcase skills, projects, and achievements
- Upload resume
- Receive messages from recruiters
- Reply to recruiter messages

### For Recruiters
- Search students by skills
- View student portfolios
- Send messages to students
- Receive student replies
- Must be approved by admin before access

### For Admins
- Approve/reject recruiter registrations
- View all users and their statistics
- Manage the platform

### For Visitors
- Browse public student portfolios
- Search students by skills
- No registration required for viewing

## Tech Stack

### Backend
- Django 5.0.6
- Django REST Framework 3.15.2
- JWT Authentication (SimpleJWT)
- SQLite (development)
- CORS headers for frontend integration

### Frontend
- React 18
- Vite (build tool)
- Tailwind CSS (styling)
- React Router (routing)
- Axios (API calls)
- React Hot Toast (notifications)

## Quick Start

### Prerequisites
- Python 3.8+
- Node.js 18+
- npm or yarn

### Backend Setup

1. **Navigate to backend directory:**
   ```bash
   cd backend
   ```

2. **Create and activate virtual environment:**
   ```bash
   python -m venv .venv
   # Windows
   .venv\Scripts\activate
   # macOS/Linux
   source .venv/bin/activate
   ```

3. **Install dependencies:**
   ```bash
   pip install django==5.0.6 djangorestframework==3.15.2 djangorestframework-simplejwt==5.3.1 django-cors-headers==4.4.0 Pillow==10.4.0
   ```

4. **Run migrations:**
   ```bash
   python manage.py migrate
   ```

5. **Create admin user:**
   ```bash
   python create_admin.py
   ```

6. **Start the development server:**
   ```bash
   python manage.py runserver
   ```

The backend will be available at `http://localhost:8000`

### Frontend Setup

1. **Navigate to frontend directory:**
   ```bash
   cd frontend
   ```

2. **Install dependencies:**
   ```bash
   npm install
   ```

3. **Start the development server:**
   ```bash
   npm run dev
   ```

The frontend will be available at `http://localhost:3000`

## Default Admin Credentials

- **Username:** admin
- **Password:** admin123
- **Role:** Admin

## API Endpoints

### Authentication
- `POST /api/auth/login/` - Login
- `POST /api/auth/refresh/` - Refresh JWT token
- `POST /api/auth/register/student/` - Student registration
- `POST /api/auth/register/recruiter/` - Recruiter registration

### Students
- `GET /api/students/public/` - Get all public student profiles
- `GET /api/students/me/` - Get current student profile
- `PUT /api/students/me/` - Update current student profile

### Projects
- `GET /api/projects/` - Get current student's projects
- `POST /api/projects/` - Create new project
- `PUT /api/projects/{id}/` - Update project
- `DELETE /api/projects/{id}/` - Delete project

### Recruiters
- `GET /api/recruiters/search/?skill=python` - Search students by skill

### Admin
- `GET /api/admin/recruiters/` - Get all recruiters
- `PATCH /api/admin/recruiters/{id}/approve/` - Approve recruiter
- `GET /api/admin/users/` - Get all users

### Messages
- `GET /api/messages/` - Get user's messages
- `POST /api/messages/` - Send message

### Skills
- `GET /api/skills/` - Get all skills
- `POST /api/skills/` - Create new skill

## Project Structure

```
SKILL_SCAPE/
├── backend/
│   ├── accounts/          # User management, authentication
│   ├── portfolio/         # Student projects
│   ├── messaging/         # Recruiter-student messaging
│   ├── skillscape/        # Django settings
│   └── manage.py
├── frontend/
│   ├── src/
│   │   ├── components/    # Reusable components
│   │   ├── pages/         # Page components
│   │   ├── context/       # React context (auth)
│   │   ├── api/           # API client
│   │   └── hooks/         # Custom hooks
│   ├── public/
│   └── package.json
└── README.md
```

## Development

### Backend Development
- The Django admin is available at `http://localhost:8000/admin/`
- API documentation can be viewed at `http://localhost:8000/api/`
- Use the admin credentials to access the admin panel

### Frontend Development
- The React app runs on `http://localhost:3000`
- Hot reload is enabled for development
- API calls are proxied to the Django backend

## Deployment

### Backend Deployment
1. Set `DEBUG = False` in settings.py
2. Configure proper database (PostgreSQL recommended)
3. Set up static file serving
4. Configure CORS for your domain
5. Set up environment variables for secrets

### Frontend Deployment
1. Build the production version: `npm run build`
2. Serve the `dist/` folder with a web server
3. Update API base URL in production

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

## License

This project is licensed under the MIT License.





