Rodny Portfolio CMS

A modern, responsive developer portfolio powered by PHP, JavaScript, and MySQL. The project is designed to showcase development skills, featured projects, and contact information through a public portfolio website, with a foundation for future content management and administrative features.

Live website: https://rodny.free.nf/

⸻

Overview

Rodny Portfolio CMS is a personal portfolio website built to present technical expertise, demonstrate completed projects, and make it easy for visitors to get in touch.

The application uses PHP for server-side processing, MySQL for persistent data storage, and JavaScript for interactive user experiences. Its modular structure separates database configuration, session initialization, styling, and browser-side functionality.

The long-term goal is to develop the website into a secure, database-driven content management system with an administrative dashboard.

Features

Public portfolio

* Responsive portfolio homepage.
* Introduction and About section.
* Dynamic skills loaded from MySQL.
* Featured projects loaded from MySQL.
* Project descriptions, technologies, images, and external links.
* Contact form interface.
* Social links and navigation.
* Responsive layouts for desktop and mobile devices.

Backend

* PHP-powered server-side rendering.
* PDO-based MySQL database connectivity.
* Database-driven skills and projects.
* Session initialization.
* CSRF token generation for the contact form.
* Error logging without intentionally exposing technical details to visitors.
* HTML output escaping for database content.

Planned CMS enhancements

* Secure administrator login and logout.
* Dashboard for managing projects and skills.
* Contact-message management.
* Project image uploads and media management.
* Stronger role and permission controls.
* Improved validation, rate limiting, and abuse prevention.
* Optional Telegram bot integration.
* Optional AI-assisted portfolio features.

Planned features are not necessarily implemented in the current version.

⸻

Technology Stack

Technology	Purpose
PHP 8.x	Backend logic and server-side rendering
JavaScript	Browser interactions and form behavior
MySQL	Persistent application data
PDO	Database access and prepared statements
HTML5	Page structure
CSS3	Responsive design and visual styling
Font Awesome	Icons
InfinityFree	Current hosting environment

⸻

Project Structure

portfolio-cms/
├── index.php
├── config.php
├── session_bootstrap.php
├── contact_handler.php
├── favicon.ico
├── README.md
│
├── css/
│   └── style.css
│
├── js/
│   └── main.js
│
├── assets/
│   └── images/
│       └── profile-placeholder.png
│
└── admin/
    └── [administration files, if configured]

The exact directory structure may vary depending on the files installed on the hosting account.

Database

The current database includes these core tables:

* admin_users — administrator accounts.
* projects — portfolio projects.
* skills — technical skills.
* messages — contact messages.

The homepage reads skills and projects from MySQL. Administrative and contact-form functionality depends on the implementation of the corresponding PHP files.

Database setup

1. Create a MySQL database through your hosting control panel.
2. Import the project’s SQL schema using phpMyAdmin, or create the required tables.
3. Configure the connection in config.php.
4. Confirm that the database user has the necessary permissions.
5. Run the diagnostic script during development, then delete it after testing.

Do not run destructive reset scripts against a database containing data you want to keep. Back up the database before changing its schema.

Installation

Requirements

* PHP 8.x with PDO MySQL support.
* MySQL or a compatible MariaDB server.
* A web server with PHP support.
* A configured database and database user.

Local or hosted installation

1. Upload the project files to the web root, such as htdocs/.
2. Create the database and required tables.
3. Configure config.php with the correct database connection settings.
4. Ensure session_bootstrap.php initializes sessions correctly.
5. Verify that css/style.css and js/main.js are present.
6. Configure contact_handler.php if contact submissions are required.
7. Open the website and verify that the skills and projects load correctly.

Database configuration

Keep database credentials out of public repositories. Where the hosting provider supports environment variables, use them for database secrets. Otherwise, protect the configuration file from direct web access and never commit real credentials to Git.

Example connection settings:

$db_host = 'YOUR_DATABASE_HOST';
$db_name = 'YOUR_DATABASE_NAME';
$db_user = 'YOUR_DATABASE_USERNAME';
$db_pass = 'YOUR_DATABASE_PASSWORD';

Use the exact values provided by your hosting control panel. The example above is a placeholder, not a working connection by itself.

Security

Security is an ongoing part of the project’s development.

Recommended practices include:

* Use PDO prepared statements for all queries containing user input.
* Escape untrusted output with htmlspecialchars().
* Validate and normalize contact-form inputs on the server.
* Verify CSRF tokens when processing form submissions.
* Use secure session cookie settings and regenerate session IDs after authentication.
* Hash administrator passwords using password_hash() and verify them using password_verify().
* Keep detailed PHP errors in server logs rather than displaying them publicly.
* Restrict upload file types and sizes if image uploads are added.
* Protect configuration files and backups.
* Use HTTPS for the live website.
* Apply login rate limiting and authorization checks to every administrative action.

Important: Generating a CSRF token in the homepage does not, by itself, secure the contact form. The receiving handler must validate the token and safely process the submission. Similarly, an administrator table does not mean the admin panel is already secure.

Development Guidelines

The project prioritizes a lightweight, understandable stack:

* PHP for backend logic.
* JavaScript for client-side interactions.
* MySQL for structured data storage.

The intention is to avoid unnecessary framework dependencies and keep the code practical to maintain on shared hosting.

When extending the project, preserve existing functionality, validate changes before deployment, and back up files and database data before making major modifications.

Roadmap

* [ ]	Audit and secure the administrator panel.
* [ ]	Review database configuration and permissions.
* [ ]	Verify all homepage queries against the actual database schema.
* [ ]	Complete secure contact-form processing.
* [ ]	Implement project and skill management in the admin dashboard.
* [ ]	Add secure image upload handling.
* [ ]	Improve accessibility and mobile performance.
* [ ]	Add automated backups and deployment checks.
* [ ]	Explore optional Telegram bot integration.
* [ ]	Explore optional AI-powered portfolio assistance.

Hosting

The current public portfolio is hosted at:

https://rodny.free.nf/

Hosting features, resource limits, database access, and available PHP extensions depend on the hosting provider’s current plan and configuration.

Contributing and Feedback

This is a personal portfolio and CMS project. Suggestions, bug reports, security improvements, and ideas for future features are welcome.

Before reporting a bug, include the affected page, steps to reproduce the issue, and any relevant error message. Never include passwords, session tokens, API keys, or other secrets in an issue report.

License

No license has been specified yet. Unless a license is added to the repository, reuse and redistribution are subject to applicable copyright law.

⸻

Built with PHP, JavaScript, and MySQL.

Focused on secure development, clean code, and continuous improvement.