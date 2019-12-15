# Example site configuration

```
server {
	listen 443 ssl http2;
	server_name jeremyfelt.com;
	root /var/www/jeremyfelt.com/www/wordpress;

	ssl_certificate /etc/letsencrypt/live/jeremyfelt.com/fullchain.pem;
	ssl_certificate_key /etc/letsencrypt/live/jeremyfelt.com/privkey.pem;

	# Include the standard SSL configuration.
	include /etc/nginx/include-common-ssl.conf;

	# Include the basic location block handing requests.
	include /etc/nginx/include-common-php-initial.conf;

	# Custom location blocks for this server name can be entered here.

	# Include the rules common to handling WordPress.
	include /etc/nginx/include-common-wordpress.conf;

	# Include the location block used to properly handle PHP requests.
	include /etc/nginx/include-common-php-location.conf;
}
```
