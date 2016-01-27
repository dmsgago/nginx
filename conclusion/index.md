---
layout: index

title: Nginx
tagline: Investagación y estudio de rendimiento sobre el Servidor Web Nginx
---

### Conclusión

Tal y como hemos podido comprobar en las gráficas, Apache 2.4 con Event-FPM tiene un rendimiento muy superior a Nginx-FPM. En cualquiera de las tres cargas que hemos comprobado, Apache 2.4 ha mantenido una mejor gestión de la memoria, llegando a reducir en un 18,6% su uso (carga media). En tiempo de CPU también se ha visto superado Nginx por Apache 2.4, con una superioridad mayor que en memoria, en el estudio hemos detectado hasta un 60% (carga alta).

Además, hay que tener en cuenta la capacidad de Apache 2.4 para mantener un consumo de memoria más estable, mientras que Nginx es más irregular y hace más difícil predecir su consumo.

Queda bastante claro cual es la configuración que ofrece un mejor rendimiento y una mayor reducción de los recursos, Apache 2.4 con Event-FPM.
