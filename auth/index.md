---
layout: index

title: Nginx
tagline: Investagación y estudio de rendimiento sobre el Servidor Web Nginx
---

### Autenticación y Control de Acceso

Instalamos las utilidades de Apache, para posteriormente usar *htpasswd* para generar las credenciales de los usuarios con permiso de autenticación.

    # apt-get install -y apache2-utils

Generamos el fichero donde se almacenarán los usuarios permitidos.

    # htpasswd -c /etc/nginx/users.passwd usuario

Editamos el fichero de configuración del Sitio Web y añadimos las siguientes líneas.

    # emacs /etc/nginx/sites-available/default
        auth_basic "Restricted";
        auth_basic_user_file /etc/nginx/users.passwd;

Reiniciamos el servicio de Nginx para actualizar los cambios realizados.

    # systemctl restart nginx.service

Comprobación de acceso al sitio.

![Acceso Autenticado](/nginx/images/n02.png)

#### Digest

Aunque no permite esta funcionalidad por defecto, Nginx ofrece la posibilidad de instalar el módulo [ngx_http_auth_digest](https://www.nginx.com/resources/wiki/modules/auth_digest/) para implementarla.
