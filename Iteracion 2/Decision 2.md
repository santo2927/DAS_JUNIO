# Decisión sobre los distintos microservicios y sus comunicaciones

* Estado: Finalizada
* Decisores: Alejandro Fernández San Román
* Fecha: 2022/04/05

Descripción técnica: Decisión sobre los distintos microservicios y sus comunicaciones

## Contexto y declaración del problema

La aplicación ha de distribuir la anterior capa de negocio en microservicios y hemos de decidir la comunicación que habrá entre ellos

## Motivos de la decision 

* RF1.2 Microservicio de preferencias
* RF1.3 Microservicio de pedidos y compras
* RF1.4 Comunicación de microservicios
* RF1.5 Microservicio de devoluciones

## Opciones consideradas

* Comunicar los microservicios todos con todos
* Partir la comunicación entre los microservicios, especificándola y minimizando el número de canales de comunciación
* Quitar los canales de comunicación entre microservicios y únicamente mantener su comunicación a través del Gateway

## Resultado de la decisión

Opción escogida: "Partir la comunicación entre los microservicios, especificandola y minimizando el número de canales de comunciación", porque de esta manera podremos elegir que microservicios se comunican entre si.

### Consecuencias neutras

* Los microservicios de preferencias y de pedidos y compras estaran ligados únicamente a sus respectivas bases de datos, siendo el único acceso a ellas pues son las únicas que las utilizan. 
* El microservicio de devoluciones ha de comunicarse con el microservicio de compras para verificar que la compra se haya hecho y que la ha hecho el cliente que esté pidiéndolo.
* El gateway se pondrá como elemento semi-externo de la capa de negocio

### Consecuencias positivas 

* Al minimizar el número de canales podemos tomar la elección de qué microservicios se comunican entre si. 
* Se generarán menos dependencias de cara al futuro.

### Consecuencias negativas 

* Si se gestiona mal una conexión se puede general código inutil y podríamos llegar a tener datos inaccesibles.

## Pros y contras de las opciones

### Comunicar los microservicios todos con todos

* Bueno, porque abarata los costes de especificación de microservicios.
* Bueno, porque disminuye el código repetido.
* Malo, porque prácticamente dejaría de estar dividido en microservicios pues todos dependen de todos.
* Malo, porque encarece mucho la escalabilidad de la capa y dificulta añadir microservicios independientes.

### Partir la comunicación entre los microservicios, especificandola y minimiando el número de canales de comunciación


* Bueno, porque los microservicios solo se tienen que comunicar con aquellos que necesitan.
* Bueno, porque aumenta la escalabilidad manteniendo el coste en mínimos.
* Bueno, porque aumenta la velocidad del sistema al tener los microservicios comunicados entre sí y no depender del gateway.
* Malo, porque genera codigo duplicado o desperdicio temporal al comunicarte con otro microservicio para obtener un resultado.
* Malo, porque caminos mal gestionados pueden dar lugar a código inútil, así como datos inaccesibles.

### Quitar los canales de comunicación entre microservicios y únicamente mantener su comunicación a través del Gateway


* Bueno, porque simplifica añadir nuevos microservicios sin cambiar las comunicaciones anteriores.
* Bueno, porque nos permite gestionar los arcos entre los microservicios con mayor facilidad.
* Malo, porque incumple parcialmente el requisito funcional 1.4, porque no habría comunciación entre microservicios.
* Malo, porque aumenta el coste temporal de recursos compartidos entre microservicios.










