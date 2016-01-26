---
layout: index

title: Nginx
tagline: Investagación y estudio de rendimiento sobre el Servidor Web Nginx
---

### Virtual Hosting

Vamos a crear dos virtualhost. Para ello, cogeremos como base la configuración por defecto:

    # cp /etc/nginx/sites-available/default /etc/nginx/sites-available/diego
    # cp /etc/nginx/sites-available/defaultdefault /etc/nginx/sites-available/jose

Editamos el sitio de diego , por ejemplo:

    # emacs /etc/nginx/sites-available/diego
    server {

            listen 80;
    
            server_name www.diego.org;

            location / {

                    root /var/www/diego;
    
                    index index.html;

            }
    }

Creamos la estructura de directorios de los sitios:

    # mkdir /var/www/diego
    # mkdir /var/www/jose

Creamos los index.html.

Creamos un enlace simbólico en /etc/nginx/sites-enabled/ para cada uno de los sitios:

    # ln -s /etc/nginx/sites-available/diego /etc/nginx/sites-enabled/diego
    # ln -s /etc/nginx/sites-available/jose /etc/nginx/sites-enabled/jose

Por último, reiniciamos el servicio de nginx:

    # systemctl restart nginx.service

Para realizar la comprobación, editamos el fichero /etc/hosts y añadimos los dos sitios con la IP del servidor y accedemos desde el navegador:

![Sitio Diego](/nginx/images/sitiodiego.png)

![Sitio Jose](/nginx/images/sitiojose.png)
