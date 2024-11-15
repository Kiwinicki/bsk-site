# BSK example site 



## How to run it:
1. install Apache server with MySQL (or use a package like XAMPP)
2. clone repo to `/var/www/html/` (on Linux) or `C:/xampp/htdocs/` (on Windows)
3. add `.env` file here: `bsk-site/utils/.env` with these fields:
    ```toml
    DB_HOST=XXX.XXX.XXX.XXX
    DB_USER=your_usrname
    DB_PASS=your_passwd
    DB_NAME=products
    CAPTCHA_KEY=public_key
    CAPTCHA_SECRET=secret_key
    ANALYTICS_ID=google_analytics_id
    ```

## Implemented things:
- `.htaccess` with some bot user-agents blocked
- reCAPTCHA on contact form `/about.php`
- detecting webdriver (selenium) and redirecting to `bot-detected.php` (it looks like `index.php` but its filled with fake data)
- sitemaps (html and xml)
- `robots.txt` (allowing only indexing bots like Googlebot)
- honeypot (you need to set fail2ban on `/honeypot.php` visit)
- `/humans.php` disallowed in `robots.txt` (you need to add it to fail2ban to check if any bot don't applies to it)

## TODO:
- google analitics
- rate-limiting (include httpd.conf in repo)
