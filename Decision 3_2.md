# Decisión sobre los distintos módulos de la aplicación

* Estado: Finalizada
* Decisores: Alejandro Fernández San Román
* Fecha: 2022/04/05

Descripción técnica: Decisión sobre el módulo de mensajería de la aplicación

## Contexto y declaración del problema

La aplciación debe tener un módulo de mensajería soportado por un middleware independiente.

## Motivos de la decision 

* RF2.3 Módulo de mensajería

## Opciones consideradas

* Soportar el módulo de mensajería como una capa horizontal debajo de la capa de negocio
* Soportar el módulo de mensajería a través de una entidad a parte de nuestro sistema

## Resultado de la decisión

Opción escogida: "Soportar el módulo de mensajería como una capa horizontal debajo de la capa de negocio", porque tendremos más independencia, al no depender de entidades externas.

### Consecuencias positivas

* No tendremos que contactar continuamente con una empresa externa en caso de que suceda cualquier problema con el módulo.

### Consecuencias negativas

* Habría que realizar la gestión del middleware independiente RabbitMQ al no disponer de una entidad externa.

## Pros y contras de las opciones

### Soportar el módulo de mensajería como una capa horizontal debajo de la capa de negocio

* Bueno, porque nos da versatilidad e independencia a la hora de hacer crecer nuestra aplicación.
* Malo, porque aumenta los costes y el tiempo que se tarda en hacer la aplicación.
* Malo, porque el middleware tendría que ser gestionado por nosotros

### Soportar el módulo de mensajería a través de una entidad a parte de nuestro sistema

* Bueno, porque nos permite gastar tiempo en otros recursos de la aplicación.
* Malo, porque dependemos de una empresa a parte para nuestro sistema, lo que puede traer consigo problemas.
* Malo, porque el coste se mantiene en el tiempo.
