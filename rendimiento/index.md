---
layout: index

title: Nginx
tagline: Investagación y estudio de rendimiento sobre el Servidor Web Nginx
---

### Comparación de rendimiento con Apache 2.4

La comparación de rendimiento se realizará sobre 2 máquinas Debian, sirviendo un Wordpress con los distintos servidores web:

 - Apache 2.4, Event y PHP5-FPM.

 - Nginx y PHP5-FPM.

#### Carga Baja

##### APACHE 2.4

![Event carga baja](/nginx/images/n06.png)

##### NGINX

![Nginx carga baja](/nginx/images/n03.png)

| WEBSERVER  | MEMORIA |   CPU   |
| :--------- | :-----: | :-----: |
| Apache 2.4 | 59 MB   | 2,1 seg |
| Nginx      | 63 MB   | 4,6 seg |

----------------------------------

#### Carga Media

##### APACHE 2.4

![Event carga media](/nginx/images/n07.png)

##### NGINX

![Nginx carga media](/nginx/images/n04.png)

| WEBSERVER  | MEMORIA |   CPU   |
| :--------- | :-----: | :-----: |
| Apache 2.4 | 57 MB   | 9 seg   |
| Nginx      | 70 MB   | 20 seg  |

----------------------------------

#### Carga Alta

##### APACHE 2.4

![Event carga alta](/nginx/images/n08.png)

##### NGINX

![Nginx carga alta](/nginx/images/n05.png)

| WEBSERVER  | MEMORIA |   CPU   |
| :--------- | :-----: | :-----: |
| Apache 2.4 | 60 MB*  | 16 seg  |
| Nginx      | 72 MB   | 40 seg  |

----------------------------------

### Tiempos de CPU

#### Carga baja

![Tiempos de CPU con carga baja](/nginx/images/cpu01.png)

----------------------------------

#### Carga media

![Tiempos de CPU con carga media](/nginx/images/cpu02.png)

----------------------------------

#### Carga alta

![Tiempos de CPU con carga alta](/nginx/images/cpu03.png)
