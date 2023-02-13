
``
a2enmod rewrite
``
Reload apache in docker container

``
/etc/init.d/apache2 reload
``

Config for single page app like vue
```
<VirtualHost *:80>
	ServerAdmin mail@karolisdailidonis.de
	ServerName xxxx.xx
	ServerAlias xxx.xxxx.xx xyz.xxxx.xx
	DocumentRoot /var/www/html

	<Directory /var/www/html/ >
		FallbackResource /index.html

		<IfModule mod_rewrite.c>
			RewriteEngine On
			RewriteBase /
			RewriteRule ^index\.html$ - [L]
			RewriteCond %{REQUEST_FILENAME} !-f
			RewriteCond %{REQUEST_FILENAME} !-d
			RewriteRule . /index.html [L]
		</IfModule>

	</Directory>

	ErrorLog ${APACHE_LOG_DIR}/error.log
	CustomLog ${APACHE_LOG_DIR}/access.log combined

	<IfModule mod_dir.c>
		DirectoryIndex index.html
	</IfModule>
</VirtualHost>
```
