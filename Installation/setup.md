# Installation and Setup

Welcome to the **Installation and Setup** guide for CodeIgniter 3! This guide will help you get CodeIgniter 3 up and running on your system quickly and efficiently.

---

## Requirements

Before you begin, make sure your server meets the following requirements:

- **PHP version**: 5.6 or newer.
- **Database**: MySQL (5.1+) via the `mysqli` driver, PostgreSQL via the `postgre` driver, or SQLite3 via the `sqlite3` driver.
- **Web Server**: Apache with `mod_rewrite` enabled, Nginx, or any server that supports PHP.

---

## Step 1: Download CodeIgniter

1. Visit the [CodeIgniter website](https://codeigniter.com) and download the latest version of CodeIgniter 3.
2. Extract the downloaded ZIP file to your desired location on your server.

---

## Step 2: Configure the Base URL

1. Open the `application/config/config.php` file.
2. Find the following line:
   ```php
   $config['base_url'] = '';
3. Set the base_url to your website's base URL, including the trailing slash. For example:
   ```php
   $config['base_url'] = 'http://localhost/your_project_name/';

---

## Step 3: Configure the Database

1. Open the `application/config/database.php` file.
2. Set your database settings:
   ```php
   $db['default'] = array(
       'dsn'    => '',
       'hostname' => 'localhost',
       'username' => 'your_username',
       'password' => 'your_password',
       'database' => 'your_database',
       'dbdriver' => 'mysqli',
       'dbprefix' => '',
       'pconnect' => FALSE,
       'db_debug' => (ENVIRONMENT !== 'production'),
       'cache_on' => FALSE,
       'cachedir' => '',
       'char_set' => 'utf8',
       'dbcollat' => 'utf8_general_ci',
       'swap_pre' => '',
       'encrypt' => FALSE,
       'compress' => FALSE,
       'stricton' => FALSE,
       'failover' => array(),
       'save_queries' => TRUE
   );

---

## Step 4: Set Up URL Rewriting

To use clean URLs (pretty URLs) with CodeIgniter, you need to set up URL rewriting.

### For Apache:

1. Ensure `mod_rewrite` is enabled.
2. Create a `.htaccess` file in your project root directory with the following content:
   ```apache
   <IfModule mod_rewrite.c>
       RewriteEngine On
       RewriteBase /your_project_name/
       RewriteCond %{REQUEST_FILENAME} !-f
       RewriteCond %{REQUEST_FILENAME} !-d
       RewriteRule ^(.*)$ index.php/$1 [L]
   </IfModule>

### For Nginx:

1. Open your Nginx server block configuration file.
2. Add the following location block:
   ```nginx
   location / {
    try_files $uri $uri/ /index.php?$query_string;
   }

---

## Step 5: Test the Installation

1. Open your web browser.
2. Navigate to your project URL (e.g., `http://localhost/your_project_name/`).
3. You should see the default CodeIgniter welcome page.

---

## Troubleshooting

### Common Issues

- **404 Page Not Found**: Ensure your `base_url` is correctly set and your `.htaccess` file is properly configured.
- **Database Connection Errors**: Double-check your database configuration settings in `application/config/database.php`.

---

Congratulations! You have successfully installed and set up CodeIgniter 3. You are now ready to start building your application. If you encounter any issues, refer to the [CodeIgniter User Guide](https://codeigniter.com/userguide3/) for further assistance.

Happy coding!

   
