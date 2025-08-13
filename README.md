# Laravel 12 Deployment on Railway

This guide will help you deploy a Laravel 12 application to Railway with MySQL.

## Prerequisites

-   Railway account
-   GitHub repository for your Laravel project
-   MySQL service created in Railway

## Steps

### 1. Clone your repository

```bash
git clone https://github.com/snlt11/laravel12-railway
cd https://github.com/snlt11/laravel12-railway
```

### 2. Set up Railway project

-   Create a new Railway project
-   Add a MySQL service
-   Link your GitHub repository to Railway

### 3. Configure environment variables

In Railway dashboard, go to your service's **Variables** tab and set:

```
DB_CONNECTION=mysql
DB_HOST=${{MySQL.MYSQLHOST}}
DB_PORT=${{MySQL.MYSQLPORT}}
DB_DATABASE=${{MySQL.MYSQLDATABASE}}
DB_USERNAME=${{MySQL.MYSQLUSER}}
DB_PASSWORD=${{MySQL.MYSQLPASSWORD}}
```

### 4. Push your code

```bash
git add .
git commit -m "Initial Railway deploy config"
git push
```

### 5. Deploy on Railway

-   Railway will build and deploy your app automatically
-   Migrations will run on startup

### 6. Access your app

-   Visit the Railway-provided URL to see your Laravel app live

## Troubleshooting

-   If you see database errors, check your environment variable references and MySQL service status
-   Make sure your PHP version matches your Laravel requirements
-   Use Railway logs for debugging

## Troubleshooting: Use Direct Database URL

If you encounter connection errors with environment variables, you can use direct database credentials in your `.env` file for testing (do NOT use real credentials in public repos):

```
DB_CONNECTION="mysql"
DB_HOST="railway.proxy.railway.net"
DB_PORT="11223344"
DB_DATABASE="railway"
DB_USERNAME="root"
DB_PASSWORD="your_password_here"
```

Replace `your_password_here` with your actual password. Remove these before sharing your code publicly.

---

**Enjoy your Laravel 12 app on Railway!**
