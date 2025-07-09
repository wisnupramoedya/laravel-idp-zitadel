# Laravel Vue SSO with Zitadel

A sample application demonstrating how to implement Single Sign-On (SSO) authentication in a Laravel backend with Vue.js Inertia frontend using Zitadel as the Identity Provider.

## Notice

This project is still underdevelopment

## Overview

This project showcases a modern web application architecture with:

- Backend: Laravel with JWT authentication
- Frontend: Vue.js Inertia with SSO integration
- Identity Provider: Zitadel for centralized authentication and authorization
- Authentication Flow: OAuth 2.0 / OpenID Connect

## Features

- 🔐 Single Sign-On authentication via Zitadel
- 🚀 Laravel with protected routes
- ⚡ Vue.js inertia
- 🔄 Automatic token refresh
- 🛡️ Role-based access control
- 📱 Responsive design
- 🔒 Secure logout with session cleanup

## Prerequisites

- PHP 8.1 or higher
- Composer
- Node.js 16+ and npm/yarn
- MySQL/PostgreSQL database
- Zitadel instance (cloud or self-hosted)

## Installation

1. Clone the Repository
    ```bash
    git clone github.com/wisnupramoedya/laravel-idp-zitadel
    cd laravel-idp-zitadel
    ```
2. Backend Setup (Laravel)

    ```bash
    # Install PHP dependencies
    composer install

    # Copy environment file
    cp .env.example .env

    # Generate application key
    php artisan key:generate

    # Configure database connection in .env
    DB_CONNECTION=mysql
    DB_HOST=127.0.0.1
    DB_PORT=3306
    DB_DATABASE=your_database
    DB_USERNAME=your_username
    DB_PASSWORD=your_password

    # Run migrations
    php artisan migrate

    # Start Laravel development server
    php artisan serve
    ```

3. Frontend Setup (Vue.js)

    ```bash
    # Navigate to frontend directory
    cd frontend

    # Install dependencies

    npm install

    # Start development server

    npm run dev

    ```

## Zitadel Configuration

1. Create Zitadel Application

    1. Log in to your Zitadel console
    2. Navigate to Projects → Your Project → Applications
    3. Click New Application
    4. Choose Web Application
    5. Configure the following settings:

    ```
    Application Name: Laravel Vue SSO
    Authentication Method: PKCE
    Redirect URIs:

    - http://localhost:8080/auth/callback
    - http://localhost:3000/auth/callback
    Post Logout Redirect URIs:
    - http://localhost:8080/
    - http://localhost:3000/
    ```

2. Environment Configuration
   Update your .env file with Zitadel credentials:

    ```env
    # Zitadel Configuration
    ZITADEL_DOMAIN=your-instance.zitadel.cloud
    ZITADEL_CLIENT_ID=your-client-id
    ZITADEL_PROJECT_ID=your-project-id
    ```

## API Endpoints

### Authentication

POST /api/auth/login - Initiate SSO login
POST /api/auth/callback - Handle OAuth callback
POST /api/auth/logout - Logout and revoke tokens
POST /api/auth/refresh - Refresh access token

### Protected Routes

GET /api/user - Get current user information
GET /api/dashboard - Protected dashboard data

## Security Considerations

- Always use HTTPS in production
- Implement proper CORS configuration
- Validate JWT tokens on each request
- Use secure session storage
- Implement rate limiting
- Regular security updates

## Troubleshooting

### Common Issues

**under development**

## License

This project is open-sourced software licensed under the MIT license.

## Support

For issues and questions:

- Check the Issues page
- [Zitadel Documentation](https://zitadel.com/docs/)
- [Laravel Documentation](https://laravel.com/docs)
- [Vue.js Documentation](https://vuejs.org/guide/)
