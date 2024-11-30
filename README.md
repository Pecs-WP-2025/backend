<p align="center"><a href="https://laravel.com" target="_blank"><img src="https://raw.githubusercontent.com/laravel/art/master/logo-lockup/5%20SVG/2%20CMYK/1%20Full%20Color/laravel-logolockup-cmyk-red.svg" width="400" alt="Laravel Logo"></a></p>

<p align="center">
<a href="https://github.com/laravel/framework/actions"><img src="https://github.com/laravel/framework/workflows/tests/badge.svg" alt="Build Status"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/dt/laravel/framework" alt="Total Downloads"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/v/laravel/framework" alt="Latest Stable Version"></a>
<a href="https://packagist.org/packages/laravel/framework"><img src="https://img.shields.io/packagist/l/laravel/framework" alt="License"></a>
</p>

## About Laravel

Laravel is a web application framework with expressive, elegant syntax. We believe development must be an enjoyable and creative experience to be truly fulfilling. Laravel takes the pain out of development by easing common tasks used in many web projects, such as:

- [Simple, fast routing engine](https://laravel.com/docs/routing).
- [Powerful dependency injection container](https://laravel.com/docs/container).
- Multiple back-ends for [session](https://laravel.com/docs/session) and [cache](https://laravel.com/docs/cache) storage.
- Expressive, intuitive [database ORM](https://laravel.com/docs/eloquent).
- Database agnostic [schema migrations](https://laravel.com/docs/migrations).
- [Robust background job processing](https://laravel.com/docs/queues).
- [Real-time event broadcasting](https://laravel.com/docs/broadcasting).

Laravel is accessible, powerful, and provides tools required for large, robust applications.

## Learning Laravel

Laravel has the most extensive and thorough [documentation](https://laravel.com/docs) and video tutorial library of all modern web application frameworks, making it a breeze to get started with the framework.

You may also try the [Laravel Bootcamp](https://bootcamp.laravel.com), where you will be guided through building a modern Laravel application from scratch.

If you don't feel like reading, [Laracasts](https://laracasts.com) can help. Laracasts contains thousands of video tutorials on a range of topics including Laravel, modern PHP, unit testing, and JavaScript. Boost your skills by digging into our comprehensive video library.

## Laravel Sponsors

We would like to extend our thanks to the following sponsors for funding Laravel development. If you are interested in becoming a sponsor, please visit the [Laravel Partners program](https://partners.laravel.com).

### Premium Partners

- **[Vehikl](https://vehikl.com/)**
- **[Tighten Co.](https://tighten.co)**
- **[WebReinvent](https://webreinvent.com/)**
- **[Kirschbaum Development Group](https://kirschbaumdevelopment.com)**
- **[64 Robots](https://64robots.com)**
- **[Curotec](https://www.curotec.com/services/technologies/laravel/)**
- **[Cyber-Duck](https://cyber-duck.co.uk)**
- **[DevSquad](https://devsquad.com/hire-laravel-developers)**
- **[Jump24](https://jump24.co.uk)**
- **[Redberry](https://redberry.international/laravel/)**
- **[Active Logic](https://activelogic.com)**
- **[byte5](https://byte5.de)**
- **[OP.GG](https://op.gg)**

## Contributing

Thank you for considering contributing to the Laravel framework! The contribution guide can be found in the [Laravel documentation](https://laravel.com/docs/contributions).

## Code of Conduct

In order to ensure that the Laravel community is welcoming to all, please review and abide by the [Code of Conduct](https://laravel.com/docs/contributions#code-of-conduct).

## Security Vulnerabilities

If you discover a security vulnerability within Laravel, please send an e-mail to Taylor Otwell via [taylor@laravel.com](mailto:taylor@laravel.com). All security vulnerabilities will be promptly addressed.

## License

The Laravel framework is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).

# Backend Setup and Execution Guide

This document provides a step-by-step guide to setting up and running the backend of the project using Laravel. It includes installation instructions, essential commands, and brief explanations to help you get started quickly.

## Table of Contents

1. [Backend Installation](#backend-installation)
   - [Laravel Installation](#laravel-installation)
2. [Backend Project Execution](#backend-project-execution)
   - [1. Enable CORS](#1-enable-cors)
   - [2. Install JWT Authentication](#2-install-jwt-authentication)
   - [3. Create Migrations and Models](#3-create-migrations-and-models)
   - [4. Test APIs](#4-test-apis)
   - [5. JWT Authentication Setup](#5-jwt-authentication-setup)
   - [6. Create Table for Database Sessions](#6-create-table-for-database-sessions)
   - [7. Create Models and Controllers](#7-create-models-and-controllers)
3. [Backend Useful Commands](#backend-useful-commands)

---

## Backend Installation

### Laravel Installation

1. **Install PHP** (if not already installed):

   `brew install php`

2. **Install Composer**:

   Download and install Composer from the [official website](https://getcomposer.org/download/).

3. **Install Laravel via Composer**:

   `composer global require laravel/installer`

4. **Configure Composer's Global Bin Directory**:

   `composer global config bin-dir --absolute`

5. **Add Laravel to the System PATH**:

   Ensure that the Laravel executable is in your system's PATH so that the `laravel` command is available globally.

6. **Create a New Laravel Application**:

   - Create a new Laravel project: `laravel new my-laravel-app`
   - Navigate into the project directory: `cd my-laravel-app`

7. **Set Up Environment Variables**:

   Copy the example environment file: `cp .env.example .env`

8. **Generate Application Key**:

   `php artisan key:generate`

9. **Install Dependencies**:

   - Install project dependencies: `composer install`
   - Update composer packages: `composer update`

10. **Run Migrations**:

    `php artisan migrate`

11. **Serve the Application**:

    `php artisan serve`

---

## Backend Project Execution

### 1. Enable CORS

Install the CORS (Cross-Origin Resource Sharing) package to handle cross-origin requests:

`composer require fruitcake/laravel-cors`

### 2. Install JWT Authentication

Install and configure JSON Web Token (JWT) authentication:

1. **Install JWT Package**:

   `composer require tymon/jwt-auth`

2. **Publish Vendor Files**:

   `php artisan vendor:publish --provider="Tymon\JWTAuth\Providers\LaravelServiceProvider"`

3. **Generate JWT Secret**:

   `php artisan jwt:secret`

4. **Create Authentication Controller**:

   `php artisan make:controller AuthController`

### 3. Create Migrations and Models

Create necessary tables and corresponding models, controllers, factories, and seeders:

1. **Create Migrations**:

   - **Posts Table**: `php artisan make:migration create_posts_table`
   - **Users Table**, **Tokens Table**, **Roles Table**: Create migrations as needed.

2. **Create Models**:

   - **Post Model**: `php artisan make:model Post`

3. **Create Controllers**:

   - **Post Controller**: `php artisan make:controller PostController --resource`

??? from here until ???END lines may have been inserted/deleted
4. **Create Factories**:

   - **Post Factory**: `php artisan make:factory PostFactory --model=Post`

5. **Create Seeders**:

   - **Post Seeder**: `php artisan make:seeder PostSeeder`

6. **Seed the Database**:

   Populate the database with fake data: `php artisan db:seed`

### 4. Test APIs

Test the various APIs to ensure they are working correctly.

1. **Test Posts API**:

   `curl -X GET "http://127.0.0.1:8000/api/posts"`

2. **Test Register API**

3. **Test Login API**

4. **Test Logout API**

*Note: Replace the API endpoints with the correct URLs and include any necessary headers or payloads.*

### 5. JWT Authentication Setup

If you encounter issues with the `tymon/jwt-auth` package, consider using an alternative package.

1. **Install Alternative JWT Package**:

   `composer require php-open-source-saver/jwt-auth`

2. **Publish Vendor Files**:

   `php artisan vendor:publish --provider="PHPOpenSourceSaver\JWTAuth\Providers\LaravelServiceProvider"`

3. **Generate JWT Secret**:

   `php artisan jwt:secret`

### 6. Create Table for Database Sessions

Create a table to store session data in the database:

`php artisan session:table`

### 7. Create Models and Controllers

1. **Create User Model**:

   `php artisan make:model User`

2. **Create Post Model**:

   *(Already created in step 3)*

3. **Create JWT Response Model**:

   Create a model or service to handle JWT responses.

4. **Create Data Responses**:

   Define standard data response formats.

5. **Create Authentication Middleware**:

   `php artisan make:middleware AuthMiddleware`

6. **Add Database Factories**:

   Create factories for other models as needed.

7. **Add Database Seeders**:

   Create seeders for other models as needed.

8. **Create HTTP Routes**:

   Define routes in `routes/web.php` or `routes/api.php`.

---

## Backend Useful Commands

- **Create Migration for Default Timestamps in Posts Table**:

  `php artisan make:migration posts_default_timestamps`

- **Create Session Table**:

  `php artisan session:table`

- **List All Routes**:

  `php artisan route:list`

---

