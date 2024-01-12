- https://github.com/CharlesChiuGit/Logseq-Git-Sync-101
- https://github.com/logseq/publish-spa
- Set the GitHub action to point to logseq.cameronbrooks.net
- Add CNAME record on google cloud console for logseq.cameronbrooks.net
- I had to add this to the .htaccess on the apache server
	- ```
	  RewriteEngine On
	  RewriteCond %{HTTP_HOST} ^example\.com$ [NC]
	  RewriteRule ^(.*)$ http://www.example.com/$1 [R=301,L]
	  ```