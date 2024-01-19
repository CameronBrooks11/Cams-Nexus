# Apache and PHP Setup on Windows
- ## Step 1: Install Apache
- **Download Apache**
	- Visit [Apache Lounge](https://www.apachelounge.com/download/) and download the appropriate version for your Windows architecture.
- **Extract Files**
	- Extract the Apache files to a directory, e.g., `C:\Apache24`.
- **Open Terminal as Administrator**
	- Search and run "Command Prompt" as administrator.
- **Install Apache Service**
	- Navigate to the Apache bin directory: `cd C:\Apache24\Apache24\bin`
	- Install Apache as a service: `httpd.exe -k install`
- **Start Apache Service**
	- Start the service: `httpd.exe -k start`
- **Verify Installation**
	- Open `http://localhost` in a web browser to see the Apache test page.
- ## Step 2: Install PHP
- **Download PHP**
	- Go to [PHP for Windows](https://windows.php.net/download) and download the latest Thread Safe PHP version.
- **Extract PHP**
	- Extract PHP files to a directory, e.g., `C:\php`.
- **Configure PHP with Apache**
	- Rename `php.ini-development` to `php.ini` in your PHP directory.
	- Edit `php.ini` and update:
		- `extension_dir = "ext"`
		- Uncomment extensions like `extension=curl`, `extension=gd2`, etc.
- **Configure Apache to Use PHP**
	- Edit Apache's `httpd.conf` file in `C:\Apache24\conf`.
	- Add these lines at the end:
	  ```
	  PHPIniDir "C:/php"
	  AddHandler application/x-httpd-php .php
	  LoadModule php_module "C:/php/php7apache2_4.dll"
	  ```
		- Adjust `php7apache2_4.dll` to your PHP version.
- **Restart Apache Service**
	- Restart Apache: `httpd.exe -k restart`
- ## Step 3: Test PHP
- **Create a PHP File**
	- Create `info.php` in `C:\Apache24\htdocs` with:
	  ```php
	  <?php
	  phpinfo();
	  ?>
	  ```
- **Test PHP**
	- Visit `http://localhost/info.php` in a browser.