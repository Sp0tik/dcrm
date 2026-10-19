# DCRM — Customer Relationship Management System

A web-based Customer Relationship Management (CRM) application built with Python and Django. The project demonstrates the development of a database-driven web application using Django's core features, server-side logic, templates, and database migrations.

## Table of Contents

- [Overview](#overview)
- [Objectives](#objectives)
- [Features](#features)
- [Technology Stack](#technology-stack)
- [Project Architecture](#project-architecture)
- [Prerequisites](#prerequisites)
- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [Database Setup](#database-setup)
- [Running the Application](#running-the-application)
- [Development Workflow](#development-workflow)
- [Testing](#testing)
- [Security Considerations](#security-considerations)
- [Troubleshooting](#troubleshooting)
- [Future Improvements](#future-improvements)
- [Contributing](#contributing)
- [License](#license)

## Overview

DCRM is a Django-based web application focused on customer relationship management. It provides a foundation for organizing customer-related information through a web interface and working with persistent data using a relational database.

The project was developed to practice and demonstrate practical Python backend and web development concepts, including request handling, database interaction, application configuration, and the Model–View–Template (MVT) architecture.

### Project Goals

- Build a structured web application using Django.
- Organize application logic into reusable components.
- Work with database models and migrations.
- Connect server-side functionality with HTML templates.
- Follow a maintainable project structure.
- Establish a foundation for additional CRM functionality.

## Features

The following sections describe the intended scope of the application. Keep each feature in this list only if it is implemented and working in the current version.

### Core Application

- **Customer management** — organize and access customer information.
- **Database integration** — persist application data using Django's database layer.
- **Server-rendered pages** — display application content through Django templates.
- **Form processing** — accept and process user input where supported.
- **Data validation** — validate submitted information using the application's forms and models.
- **Database migrations** — manage database schema changes through Django migrations.

### User Access

If implemented in the project:

- User registration and authentication.
- Login and logout functionality.
- Access restrictions for authenticated users.
- User-specific data and permissions.

### Potential Extensions

The following are possible improvements, not claims about existing functionality:

- Customer search, filtering, and pagination.
- Customer activity history and notes.
- Contact and company management.
- Sales pipeline and deal tracking.
- Task assignment and follow-up reminders.
- Dashboard metrics and reporting.
- Role-based permissions.
- REST API integration.

## Technology Stack

| Technology | Purpose |
|---|---|
| Python | Main programming language |
| Django | Backend web framework |
| HTML5 | Page structure |
| CSS3 | Styling and layout |
| Django Templates | Server-side rendering |
| Relational database | Persistent application data |
| Git | Version control |

**Database:** Confirm the configured database in the project's Django settings before listing a specific engine such as SQLite or PostgreSQL.

**Additional dependencies:** Refer to `requirements.txt` for the exact Python packages used by the application.

## Project Architecture

DCRM follows Django's Model–View–Template (MVT) architectural pattern.

### Models

Models define the structure of application data and describe how records are stored in the database. Django's ORM provides an interface for creating, retrieving, updating, and deleting records without requiring raw SQL for every operation.

### Views

Views process incoming HTTP requests, execute application logic, interact with models, and return an appropriate HTTP response.

### Templates

Django templates render dynamic HTML pages using data provided by views. This separates page presentation from the majority of the server-side application logic.

### URL Routing

Django's URL configuration maps incoming paths to the corresponding views, providing a clear structure for navigating the application.

### Database Migrations

Django migrations track changes to model definitions and apply those changes to the database schema in a controlled manner.

## Prerequisites

Before running the project, make sure the following tools are installed:

- Python 3
- pip
- Git
- A terminal or command-line interface
- A supported database, if the project is configured to use an external database

Check your Python and pip installations:

```bash
python --version
python -m pip --version
git --version
```

On some systems, the Python executable may be available as `python3` rather than `python`.

## Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/Sp0tik/dcrm.git
cd dcrm
```

### 2. Create a Virtual Environment

A virtual environment isolates the project's dependencies from other Python applications on your computer.

**Windows — PowerShell**

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

If PowerShell blocks activation, you can use the virtual environment's Python executable directly or follow the Python documentation for your system's execution-policy configuration.

**Linux / macOS**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install Dependencies

If the repository contains a `requirements.txt` file, install the listed dependencies:

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

If dependency installation fails, check the Python version required by the project and review the error message before installing additional packages.

### 4. Configure Environment Variables

If the application uses environment variables, create a local environment file using the variable names expected by the project.

For example, an environment file may contain settings such as:

```dotenv
SECRET_KEY=replace-with-a-unique-local-secret
DEBUG=True
```

These are illustrative examples, not a guarantee that the current project reads these exact variables. Check the Django settings and installed configuration packages to determine the actual names and defaults.

Do not commit real secrets, production credentials, database passwords, or private API keys to the repository.

### 5. Apply Database Migrations

From the directory containing `manage.py`, run:

```bash
python manage.py migrate
```

This applies the migrations required by the project's installed Django applications.

### 6. Create an Administrator Account

If the project uses Django's standard administration system, create a superuser:

```bash
python manage.py createsuperuser
```

Follow the prompts to configure the account. This step is only necessary if you need access to the Django admin interface.

### 7. Start the Development Server

```bash
python manage.py runserver
```

Open the local development address:

http://127.0.0.1:8000/

The available pages and routes depend on the URL configuration included in the current version of the project.

Stop the development server by pressing `Ctrl+C` in the terminal.

## Configuration

Django settings control the application's behavior, including installed applications, middleware, URL routing, database configuration, static files, templates, and security options.

Before running the application in a different environment, review the project's settings and confirm the following:

- The correct database engine and connection details are configured.
- Secret values are supplied securely.
- Debug mode is disabled in production.
- Allowed hosts are configured for the deployment environment.
- Static files are configured correctly.
- Dependencies are installed in the active virtual environment.

Avoid publishing local configuration files that contain credentials or machine-specific paths.

## Database Setup

Django's ORM provides the interface between application models and the configured database.

Common database management commands include:

```bash
# Apply pending migrations
python manage.py migrate

# Show migration status
python manage.py showmigrations

# Create migration files after model changes
python manage.py makemigrations

# Open the Django interactive shell
python manage.py shell
```

Create new migrations when model definitions change, review the generated migration files, and apply them to the development database before testing the affected functionality.

The actual database engine is determined by the project's configuration. Do not assume that SQLite or PostgreSQL is being used without checking the settings.

## Running the Application

A typical local development workflow is:

1. Activate the virtual environment.
2. Install any missing dependencies.
3. Configure the required environment variables.
4. Apply database migrations.
5. Start the Django development server.
6. Open the application in a browser.
7. Test the relevant pages and workflows.
8. Review the terminal output if errors occur.

The built-in Django development server is intended for local development and testing. It should not be used as the production web server for a public deployment.

## Development Workflow

### Checking the Project Configuration

```bash
python manage.py check
```

This runs Django's system checks and reports common configuration issues.

### Creating Database Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

Review migration files before applying changes, especially when modifying existing models or removing fields.

### Running Tests

```bash
python manage.py test
```

This command runs tests discovered by Django's test framework. Its usefulness depends on whether the project contains an appropriate test suite.

### Inspecting Available Management Commands

```bash
python manage.py help
```

Django management commands can help with development, database maintenance, testing, and application administration.

## Testing

Testing is important for verifying application behavior and preventing regressions.

Areas worth testing include:

- Model validation and database operations.
- Form validation and invalid input handling.
- URL routing and expected HTTP responses.
- Authentication and access restrictions, if implemented.
- Customer creation, retrieval, updates, and deletion, if supported.
- Error handling for missing or invalid records.
- Database behavior during schema changes.

The presence of a test command does not imply that the project already has comprehensive automated tests. Report test coverage or passing test counts only after running the relevant tests and confirming the results.

## Security Considerations

Security settings must be reviewed before exposing a Django application to the internet.

### Secret Management

- Keep secret keys and credentials out of source code.
- Use environment variables or an appropriate secrets manager.
- Rotate any real credentials that have accidentally been exposed.
- Review Git history if secrets were committed previously.

### Debug Mode

Set `DEBUG=False` in production. Debug mode can expose internal application details and should not be enabled on a public production deployment.

### Allowed Hosts

Configure `ALLOWED_HOSTS` for the domains that should serve the application. Avoid using unrestricted host settings in production.

### Authentication and Authorization

If the application includes protected pages, verify that access restrictions are enforced server-side rather than relying only on hiding interface elements.

### Dependencies

Keep dependencies maintained and review package updates for compatibility and security implications.

## Troubleshooting

### `ModuleNotFoundError`

Make sure the virtual environment is activated and the required packages are installed:

```bash
python -m pip install -r requirements.txt
```

### Database Errors

Check the database configuration, ensure the required database service is available if applicable, and apply migrations:

```bash
python manage.py migrate
```

### Missing Table Errors

A missing table can indicate unapplied migrations or a mismatch between the configured database and the one being inspected.

```bash
python manage.py showmigrations
python manage.py migrate
```

### Port Already in Use

If port `8000` is occupied, start the development server on another port:

```bash
python manage.py runserver 8001
```

Then open http://127.0.0.1:8001/.

### Static Files Not Displaying

Check the template references, static file configuration, and paths to CSS or JavaScript assets. Production static-file configuration may differ from local development.

### PowerShell Virtual Environment Activation

If activation fails, verify the environment path and Python installation. You can also run the environment's Python executable directly:

```powershell
.\.venv\Scripts\python.exe manage.py runserver
```

## Future Improvements

Possible directions for further development include:

- Expand automated tests for core workflows.
- Improve validation and error handling.
- Add customer search, filtering, and pagination.
- Introduce customer activity tracking.
- Add reporting and dashboard metrics.
- Improve accessibility and responsive layouts.
- Add structured logging.
- Document application routes and configuration.
- Add a reproducible deployment workflow.
- Introduce CI checks for tests and code quality.

These items represent potential enhancements rather than features guaranteed to exist in the current version.

## Contributing

Contributions and constructive feedback are welcome.

A suggested contribution workflow:

1. Fork the repository.
2. Create a branch for your change.
3. Implement and test the change.
4. Commit your work with a descriptive message.
5. Open a pull request describing the change and its purpose.

For substantial changes, discuss the proposed approach before investing time in a larger implementation.

## License

No license is specified in this README. Before distributing the project or accepting external contributions, choose a license and add the corresponding `LICENSE` file if appropriate.

Without an explicit license, others should not assume that they have permission to reuse, modify, or redistribute the code.

## Author

**GitHub:** [@Sp0tik](https://github.com/Sp0tik)

---

*DCRM is a software development project built to explore Python, Django, and database-driven web application development.*
