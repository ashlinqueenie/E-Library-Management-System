# E-Library Management System - Replit Project

## Project Overview
A complete, professional E-Library Management System built with Python Flask featuring:
- Role-based access control (Admin & Student)
- Book management with image and PDF uploads
- Book issuing/return system
- Modern Bootstrap 5 responsive interface
- SQLite database with SQLAlchemy ORM

## Current State
The application is fully functional and running on port 5000.

## Tech Stack
- **Backend:** Python 3.11, Flask, SQLAlchemy
- **Frontend:** Bootstrap 5, Font Awesome, Jinja2
- **Database:** SQLite
- **File Handling:** Werkzeug (secure uploads), Pillow (image processing)

## Default Credentials
- **Admin:** admin@library.com / admin123

## Key Features Implemented
1. User authentication (login, registration, password hashing)
2. Admin dashboard with statistics
3. Complete book CRUD with image/PDF uploads
4. Category management
5. Book issuing system with status tracking
6. Student dashboard for browsing books
7. Search and filter functionality
8. Responsive mobile-friendly design
9. Secure file upload handling

## Project Structure
```
├── app.py                    # Main Flask application with all routes
├── models.py                 # Database models (User, Book, Category, IssuedBook)
├── static/
│   ├── css/style.css        # Custom styling
│   └── uploads/             # Uploaded book images and PDFs
└── templates/               # All HTML templates (14 files)
```

## Recent Changes
- 2024-11-14: Complete project implementation
  - Created full Flask application with all features
  - Implemented secure authentication with role-based access control
  - Fixed security: Registration only creates student accounts (prevents privilege escalation)
  - Fixed data model: Books use proper foreign key to Categories (maintains referential integrity)
  - Built responsive Bootstrap 5 UI with 14 templates
  - Implemented secure file upload system (images & PDFs)
  - Configured workflow to run on port 5000
  - All features tested and working correctly

## Workflow Configuration
- **Name:** flask-server
- **Command:** python app.py
- **Port:** 5000 (webview)
- **Status:** Running

## User Preferences
None recorded yet.

## Architecture Decisions
1. **Foreign key relationships:** Books use category_id foreign key to Categories table for referential integrity
2. **Security-first registration:** Self-registration creates only student accounts; admins created via initialization
3. **Dual upload support:** Books can have both cover images and PDF files
4. **Session-based auth:** Simple session management for user authentication
5. **Role checking:** Decorators (@admin_required, @login_required) for access control
6. **File naming:** Timestamps added to uploaded files to prevent conflicts

## Notes for Future Sessions
- Database file: `library.db` (auto-created on first run)
- Default categories: Fiction, Non-Fiction, Science, Technology, History, Biography
- File uploads stored in: `static/uploads/`
- Max file size: 16MB
- Supported image formats: JPG, PNG, GIF
- Supported document formats: PDF only
