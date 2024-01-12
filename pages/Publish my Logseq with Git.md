- https://github.com/CharlesChiuGit/Logseq-Git-Sync-101
- https://github.com/logseq/publish-spa
- Set the GitHub action to point to logseq.cameronbrooks.net
- Add CNAME record on google cloud console for logseq.cameronbrooks.net
- I had to add this to the .htaccess on the apache server (sudo nano .htaccess)
	- ```
	  RewriteEngine On
	  RewriteCond %{HTTP_HOST} ^cameronbrooks\.net$ [NC]
	  RewriteRule ^(.*)$ http://www.cameronbrooks.net/$1 [R=301,L]
	  ```
	- restart it: sudo systemctl restart apache2
- Still didnt work
	- Gonna try and edit: sudo nano /etc/apache2/apache2.conf
	- Changed:
		- ```
		  <Directory /var/www/>
		      AllowOverride All
		  </Directory>
		  ```
	-