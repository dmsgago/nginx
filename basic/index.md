---
layout: index

title: Nginx
tagline: Investagación y estudio de rendimiento sobre el Servidor Web Nginx
---

### Configuración básica

La estructura de ficheros es la siguiente:

    drwxr-xr-x 2 root root 4096 Dec  1  2014 conf.d
    -rw-r--r-- 1 root root 1034 Dec  1  2014 fastcgi.conf
    -rw-r--r-- 1 root root  964 Dec  1  2014 fastcgi_params
    -rw-r--r-- 1 root root 2837 Dec  1  2014 koi-utf
    -rw-r--r-- 1 root root 2223 Dec  1  2014 koi-win
    -rw-r--r-- 1 root root 3957 Dec  1  2014 mime.types
    -rw-r--r-- 1 root root 1459 Dec  1  2014 nginx.conf
    -rw-r--r-- 1 root root  180 Dec  1  2014 proxy_params
    -rw-r--r-- 1 root root  596 Dec  1  2014 scgi_params
    drwxr-xr-x 2 root root 4096 Jan 25 18:12 sites-available
    drwxr-xr-x 2 root root 4096 Jan 25 18:12 sites-enabled
    drwxr-xr-x 2 root root 4096 Jan 25 18:12 snippets
    -rw-r--r-- 1 root root  623 Dec  1  2014 uwsgi_params
    -rw-r--r-- 1 root root 3071 Dec  1  2014 win-utf

Los ficheros ficheros y directorios principales son:
 
..* nginx.conf  que es el fichero de configuración principal, es decir, donde se encuentra la configuración del servidor web que afectaría a todos los virtualhost.
 
..* El directorio sites-available es donde se encuentran los ficheros de configuración de cada virtualhost.
 
..* El directorio sites-enable es donde se encuentran los enlaces simbólicos a los ficheros de configuración de los virtualhost que están activos.

En Nginx no se pueden añadir nuevos módulos una vez instalado. Para ello, tendríamos que compilarlo con los módulos y luego volver a instalarlo.
