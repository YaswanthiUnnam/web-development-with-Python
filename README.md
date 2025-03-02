# Web Development with Python
Here is a structured project report based on the provided source, "Document 20.pdf". This report outlines the steps and concepts required to build a website using Python and the Flask framework.

### Project Overview
The project aims to provide a foundational understanding of web development with Python, using Flask to create a functional website. The goal is to equip individuals with the knowledge to customise and expand upon a basic website template.

*   The tutorial focuses on back-end development.
*   Front-end styling is implemented using Bootstrap, but is not the primary focus.
*   The finished product will allow users to create accounts, log in/out, and associate information with their specific user.
*   TypingDNA is mentioned as a sponsor and a tool for authenticating users based on their typing patterns.

### Core Functionalities Covered
*   **User Sign-up:** Creating new user accounts.
*   **Database Storage:** Storing user credentials and related data in a database.
*   **User Login:** Authenticating and logging in user accounts.
*   **User Logout:** Providing the ability to log out of user accounts.
*   **Data Association:** Associating specific information (e.g., notes) with individual users.

### Project Structure
The project directory is structured as follows:

*   `flask_web_app_tutorial` (main folder)
    *   `website` (folder containing website code)
        *   `static` (folder for static files like CSS, JavaScript, images)
        *   `templates` (folder for HTML templates)
        *   `__init__.py` (initialises the website folder as a Python package)
        *   `auth.py` (stores authentication-related views/routes)
        *   `models.py` (defines database models)
        *   `views.py` (stores main views/routes for the website)
    *   `main.py` (main application file to run the web server)

### Setting Up the Project
1.  Create a main folder (e.g., `flask_web_app_tutorial`).
2.  Inside the main folder, create a `website` folder.
3.  Within the `website` folder, create two additional folders named `static` and `templates`.
4.  Create the following Python files: `main.py` (in the main folder), `__init__.py`, `auth.py`, `models.py`, and `views.py` (all inside the `website` folder).

### Installing Required Packages
The project requires the installation of the following Python packages:

*   **Flask:** A lightweight Python framework for web development.
    ```bash
    pip install flask
    ```
*   **Flask-Login:** Provides user session management for Flask.
    ```bash
    pip install flask-login
    ```
*   **Flask-SQLAlchemy:** A Flask extension that provides SQLAlchemy integration for database interactions.
    ```bash
    pip install flask-sqlalchemy
    ```

### Configuration and Setup
*   **main.py:** This file serves as the entry point for the Flask application. It imports the necessary modules and starts the web server.
    *   The `if __name__ == '__main__':` statement ensures the web server only runs when the file is executed directly.
    *   `app.run(debug=True)` starts the Flask application in debug mode, automatically rerunning the server upon code changes.
*   **views.py:** This file defines the routes (URLs) that users can access.
    *   Uses Flask's `Blueprint` to organise routes.
    *   The `@views.route('/')` decorator binds the `home` function to the root URL ("/"), so that the function will run whenever a user goes to the main page of the website.
*   **auth.py:** Handles authentication-related routes such as login, logout, and sign-up.
    *   Similar to `views.py`, it uses Flask's `Blueprint` for route organisation.
*   **\_\_init\_\_.py:** Configures the Flask application and database.
    *   Initialises the Flask app.
    *   Registers the blueprints for `views.py` and `auth.py`.
    *   Configures the SQLAlchemy database URI.
    *   Creates the database tables.
*   **models.py:** Defines the structure (schema) of the database.
    *   **User Class**: Includes fields such as `id`, `email`, `password`, and `first_name`.
    *   **Note Class**: Includes fields such as `id`, `data` (note content), `date`, and a foreign key `user_id` to associate notes with users.

### Templates and HTML
*   **Base Template (base.html):**  Serves as the foundation for all other HTML pages.
    *   Includes common elements such as the navigation bar, header, and footer.
    *   Defines blocks (`block title`, `block content`) that child templates can override.
    *   Links to Bootstrap CSS for styling.
*   **Home Template (home.html):** Extends the base template and provides content for the home page.
    *   Overrides the `title` block to set the page title.
    *   Includes a content block for the home page-specific content.
*   **Login Template (login.html) & Signup Template (signup.html):** These templates provide the forms for user login and registration.

### Key Concepts
*   **Flask Blueprints:** Used to organise routes and views into logical components.
*   **Jinja Templating:**  A templating engine that allows embedding Python code within HTML templates.
*   **Flask-SQLAlchemy:** Provides tools for interacting with databases using Python.
*   **Database Models:** Python classes that define the structure of database tables.
*   **HTTP Methods:** Understanding GET (retrieving data) and POST (submitting data) requests.
*   **Message Flashing:**  A way to display one-time notification messages to users.
*   **Password Hashing:** Securing user passwords by storing them as irreversible hashes rather than plain text.
*   **Flask-Login:** Managing user authentication and sessions.
