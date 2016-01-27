---
layout: index

title: Nginx
tagline: Investagación y estudio de rendimiento sobre el Servidor Web Nginx
---

### Ejecución de scripts PHP

Instalamos php5 y el módulo FPM.

    # apt-get install php5 php5-fpm

Editamos el fichero de configuración del sitio web que crea Nginx por defecto

    # emacs /etc/nginx/sites-available/default
        server {
        	listen 80 default_server;
	        listen [::]:80 default_server;

		root /var/www/html;
		index index.php index.html index.htm;

		server_name www.iesgn.com;

		location / {
			try_files $uri $uri/ /index.php?q=$uri&$args;
		}

		error_page 404 /404.html;
		error_page 500 502 503 504 /50x.html;

		location = /50x.html {
			root /usr/share/nginx/html;
		}

		location ~ \.php$ {
			try_files $uri =404;
			fastcgi_split_path_info ^(.+\.php)(/.+)$;
			fastcgi_pass_header Set-Cookie;
			fastcgi_pass_header Cookie;
			fastcgi_pass unix:/var/run/php5-fpm.sock;
			fastcgi_index index.php;
			include fastcgi_params;
		        fastcgi_param SCRIPT_FILENAME $document_root$fastcgi_script_name;
		}

		add_header X-Cache $upstream_cache_status;
	}

Reiniciamos los demonios Nginx y PHP5-FPM.

    # systemctl restart nginx
    # systemctl restart php5-fpm

Ya podemos instalar nuestras Aplicaciones Web en PHP.

![Instalación Wordpress](/nginx/images/n09.png)
