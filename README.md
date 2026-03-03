# E-Library Management System

A complete, professional E-Library Management System built with Python Flask, featuring role-based access control, book management with image/PDF uploads, and a modern Bootstrap 5 interface.

## Features

### Admin Features
- **Dashboard** with statistics (total books, students, issued books)
- **Book Management**
  - Add books with cover image upload (JPG, PNG, GIF)
  - Upload book PDFs for digital access
  - Edit and delete books
  - Search books by title, author, or ISBN
  - Filter by category
- **Category Management**
  - Create, view, and delete categories
- **Student Management**
  - View all registered students
  - Track books issued per student
- **Book Issuing System**
  - Issue books to students
  - Set return dates
  - Track issued/returned status
  - Mark books as returned

### Student Features
- **Browse Books** with beautiful card-based layout
- **Search and Filter** by title, author, or category
- **View Book Details** including cover images and descriptions
- **Download PDFs** when available
- **Track Issued Books** with issue/return dates

### Technical Features
- User authentication with password hashing
- Role-based access control (Admin/Student)
- Secure file upload handling
- SQLite database
- Responsive Bootstrap 5 UI
- Mobile-friendly design
- Flash messages for user feedback

## Installation & Setup

### Prerequisites
- Python 3.11 or higher
- pip (Python package manager)

### Quick Start

1. **Clone or download the project**

2. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```
   Or using uv:
   ```bash
   uv pip install flask flask-sqlalchemy werkzeug pillow
   ```

3. **Run the application**
   ```bash
   python app.py
   ```

4. **Access the application**
   - Open your browser and go to: `http://localhost:5000`
   - Or on Replit, click the webview preview

## Default Login Credentials

### Admin Account
- **Email:** admin@library.com
- **Password:** admin123

### Creating New Accounts
1. Click "Register here" on the login page
2. Fill in your details (Name, Email, Password)
3. Submit to create account (all self-registrations are created as Student accounts)

**Note:** For security, self-registration only creates Student accounts. Admin accounts must be created through the database initialization or by directly adding them to the database.

## Project Structure

```
e-library/
│
├── app.py                  # Main Flask application
├── models.py              # Database models
├── library.db            # SQLite database (auto-created)
│
├── static/
│   ├── css/
│   │   └── style.css     # Custom CSS styles
│   └── uploads/          # Uploaded images and PDFs
│
└── templates/            # HTML templates
    ├── base.html         # Base template with navbar
    ├── login.html        # Login page
    ├── register.html     # Registration page
    ├── admin_dashboard.html
    ├── admin_books.html
    ├── add_book.html
    ├── edit_book.html
    ├── manage_categories.html
    ├── view_students.html
    ├── issue_book.html
    ├── issued_books_admin.html
    ├── student_dashboard.html
    ├── student_issued_books.html
    └── view_book.html
```

## Database Schema

### Users Table
- id, name, email, password (hashed), role

### Books Table
- id, title, author, category, isbn, description
- image_path, pdf_path, added_date

### Categories Table
- id, name

### Issued Books Table
- id, user_id, book_id, issue_date, return_date, status

## Usage Guide

### For Admins

1. **Login** with admin credentials
2. **Add Categories** (Fiction, Science, Technology, etc.)
3. **Add Books**
   - Fill in book details
   - Upload cover image (optional)
   - Upload PDF (optional)
4. **Issue Books**
   - Select student
   - Select book
   - Set return date
5. **Manage** all books, categories, and students from the dashboard

### For Students

1. **Register** a new account as a student
2. **Browse Books** from the dashboard
3. **Search** for specific books
4. **View Details** and download PDFs if available
5. **Check Issued Books** in "My Books" section

## Security Features

- Password hashing using Werkzeug
- Session-based authentication
- Role-based access control
- Secure file upload with validation
- SQL injection protection via SQLAlchemy ORM
- CSRF protection via Flask sessions

## File Upload Specifications

### Allowed Image Formats
- JPG, JPEG, PNG, GIF
- Maximum file size: 16MB

### Allowed Document Formats
- PDF only
- Maximum file size: 16MB

## Customization

### Change Secret Key
Edit `app.py` and update:
```python
app.config['SECRET_KEY'] = 'your-secret-key-here'
```

### Add More Categories
Login as admin and use the "Categories" menu to add new categories.

### Modify Styling
Edit `static/css/style.css` to customize the appearance.

## Troubleshooting

### Port Already in Use
If port 5000 is busy, edit `app.py`:
```python
app.run(host='0.0.0.0', port=8080, debug=True)
```

### Database Issues
Delete `library.db` and restart the app to recreate the database with default data.

### Upload Issues
Ensure the `static/uploads/` directory has write permissions.

## Technologies Used

- **Backend:** Python Flask
- **Database:** SQLite with SQLAlchemy ORM
- **Frontend:** HTML5, CSS3, Bootstrap 5, Font Awesome
- **Authentication:** Werkzeug password hashing
- **File Handling:** Pillow (PIL) for image processing

## Future Enhancements

- Book ratings and reviews
- Favorites/bookmarks for students
- Email notifications for due dates
- Export book lists to CSV
- Advanced search filters
- Book reservation system
- Fine calculation for overdue books

## License

This project is open source and available for educational purposes.

## Support

For issues or questions, please contact the system administrator.

---

**Built with Flask & Bootstrap 5**
