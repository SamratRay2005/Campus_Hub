# Campus Hub

Campus Hub is a Flask-based web application designed for university campuses, enabling students and staff to manage lost & found items and marketplace listings seamlessly. It features user authentication, email verification, image processing, and an intuitive dashboard for tracking items.

## Table of Contents

- [Features](#features)
- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Configuration](#configuration)
- [Database Initialization & Reset](#database-initialization--reset)
- [Running the Application](#running-the-application)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Features

- **User Management**: Registration with email confirmation, login/logout via Flask-Login, guest access
- **Lost & Found**:
  - Report and browse lost or found items
  - Upload and automatically resize/optimize images
  - Mark items as found or claimed
  - Filter by category, status, priority
  - View item details and user feedback/comments
- **Marketplace**:
  - Create, edit, delete listings with images
  - Set price, category, condition, and contact info
  - Filter listings and view details
- **User Profile**:
  - Dashboard to view and manage your postings
  - Recent activity overview
- **Email Notifications**: Account confirmation via email using Flask-Mail
- **Session Management**: File-based sessions with Flask-Session
- **Data Storage**: SQLite database with foreign key support and WAL mode

## Tech Stack

- **Python** 3.12
- **Flask** Web Framework
- **Flask-Login** for user session management
- **Flask-Mail** for email confirmation
- **Flask-Session** for server-side sessions
- **SQLite** database
- **Pillow** for image processing
- **Jinja2** templating
- **HTML5 & CSS3** for frontend
- **Werkzeug** utilities

## Project Structure

```
Campus_Hub/
├── __init__.py                # Package initializer
├── Main.py                    # Application entry point
├── config.py                  # Configuration and constants
├── extensions.py              # Flask extension instances
├── models.py                  # Database schema and query functions
├── reset_db.py                # Script to reset or initialize the database
├── LICENSE                    # Project license
├── lostnfound.db              # SQLite database file (auto-generated)
├── flask_session/             # File-based session storage
├── blueprints/                # Modular Flask blueprints
│   ├── auth/                  # Authentication routes
│   ├── lost_and_found/        # Lost & Found feature routes
│   └── marketplace/           # Marketplace feature routes
├── static/                    # Static files
│   └── images/                # Uploaded item photos
├── templates/                 # Jinja2 templates
│   ├── auth/                  # Login, register, profile templates
│   ├── lost_and_found/        # Dashboard, report, detail, edit
│   └── marketplace/           # Create, dashboard, detail, edit
└── README.md                  # Project documentation
```

## Installation

```bash
# Clone the repository
git clone <repository_url>
cd Campus_Hub

# (Optional) Create and activate a virtual environment
python3 -m venv venv
source venv/bin/activate

# Install required packages
pip install Flask Flask-Login Flask-Mail Flask-Session Pillow
```

> **Note:** You may lock dependencies by generating a `requirements.txt`:
> ```bash
> pip freeze > requirements.txt
> ```

## Configuration

Rename `.env.example` to `.env` or set environment variables directly:

- `FLASK_SECRET_KEY`  : Secret key for Flask sessions
- `MAIL_SERVER`       : SMTP server (default: smtp.gmail.com)
- `MAIL_PORT`         : SMTP port (default: 587)
- `MAIL_USERNAME`     : Email address for sending confirmation
- `MAIL_PASSWORD`     : App-specific password or credentials

Alternatively, edit `config.py` to set defaults.

## Database Initialization & Reset

On first run, the database and tables auto-initialize. To manually reset or reinitialize:

```bash
python reset_db.py
```

This will recreate tables, seed default users (`admin`, `temp`), and default categories.

## Running the Application

```bash
python Main.py
```

By default, the app runs in debug mode on `http://localhost:5000`.

## Usage

1. **Register** an account or use **Continue without login** for a temporary guest user.
2. **Confirm** your email via the link sent.
3. Navigate to **Lost & Found** to report or browse items.
4. Navigate to **Marketplace** to create or browse listings.
5. Visit **Profile** to manage your submissions and view activity.

## Contributing

Contributions are welcome! Please fork the repo, create feature branches, and open pull requests. Report issues on GitHub.

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.