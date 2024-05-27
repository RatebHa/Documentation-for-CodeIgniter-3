# Troubleshooting

## Common Issues

### 404 Page Not Found

- Ensure your `base_url` is correctly set in `application/config/config.php`.
- Check that your `.htaccess` file is properly configured and located in the root of your project directory.

### Database Connection Errors

- Double-check your database configuration settings in `application/config/database.php`.
- Ensure your database server is running and accessible.

### Blank Page or PHP Errors

- Verify that error reporting is enabled in your `index.php` file:
  ```php
  error_reporting(E_ALL);
  ini_set('display_errors', 1);

### Mod_rewrite Issues (Apache)

- Ensure `mod_rewrite` is enabled in your Apache configuration.
- Verify that the `AllowOverride` directive is set to `All` for your project directory in your Apache configuration:
  ```apache
  <Directory /path/to/your/project>
    AllowOverride All
  </Directory>
