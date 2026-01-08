# :honeybee: MetaBee Website (Laravel)

MetaBee is a Laravel-based digital platform that combines a public-facing website with a gated learning environment, including video-based courses and authenticated user access.

<img src="public/images/platform-screenshot.png"></img>

## Features

### 🎓 Courses & Learning
- Course listing with search, category filters, and pagination
- Modular course structure using relational data (modules → lessons)
- Dedicated course watch pages with protected access
- Video-oriented lesson views
- Dynamic course duration calculation
- “Next lesson” and “next course” navigation
- Curriculum management stored in a relational database (migrated from JSON)

### 📊 User Progress
- Dynamic progress tracking per user
- User-specific completed lesson tracking

### 👤 User Accounts
- Auth-protected areas and dashboards
- Personal information update
- Account deletion flow
- Upgrade plan functionality

### ⭐ Reviews & Ratings
- User-generated course reviews
- Create, update, and list reviews
- Dynamic rating calculation (not stored directly on the course model)

### 🛡️ Security & Architecture
- Route protection for gated content
- Rate limiting using Laravel’s `RateLimitServiceProvider`
- Clean controller separation (e.g., dedicated course watch controller)
- Reusable Blade components and view refactoring

## Usage

#### Install composer dependencies

```
composer install
```

#### Install NPM dependencies and build assets

```
npm install
npm run build
```

#### Add .env Variables

Rename the `.env.example` file to `.env` and add your database values. Change driver and port as needed.

```
DB_CONNECTION=pgsql
DB_HOST=127.0.0.1
DB_PORT=5432
DB_DATABASE=
DB_USERNAME=
DB_PASSWORD=
```

#### Run Migrations

```
php artisan migrate
```

#### Seed Database (Optional)

You can seed the database with users and courses.

```
php artisan db:seed
```

You will have a test user available with the following credentials:

-   Email: clistenes@metabee.com
-   Password: 12345678


### Setup the Storage Symlink

```
php artisan storage:link 
```

Setup the symlink to public storage for displaying user uploaded images

#### Run Server

If you are using artisan to serve, run the following:

```
php artisan serve
```

Open http://localhost:8000
