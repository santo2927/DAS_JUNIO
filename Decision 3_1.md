# Decisión sobre los distintos módulos de la aplicación

* Estado: Finalizada
* Decisores: Alejandro Fernández San Román
* Fecha: 2022/04/05

Descripción técnica: Decisión sobre el módulo de pagos de la aplicación

## Contexto y declaración del problema

La aplciación debe de permitir gestionar pagos y poder validarlos.

## Motivos de la decision 

* RF2.2 Módulo de pagos

## Opciones consideradas

* Tener una comunicación directa con banco central que gestione y valide la compra.
* Gestionar la validación de los pagos desde un plugin o un módulo externo a nuestra aplicación.

## Resultado de la decisión

Opción escogida: "Tener una comunicación directa con banco central que gestione y valide la compra", porque nos interesa tener todo centralizado en nuestra aplicación y no depender de empresas externas.

### Consecuencias neutras

* Se pondrá dentro del UML como una clase el banco central para así plasmar en el diseño que la comunicación con el banco central existe.
* Para la comunicación con el banco podemos tener una clase dentro del microservicio de compras que almacene los datos bancarios del usuario que está haciendo la compra en ese momento.

### Consecuencias positivas

* Ahorramos tiempo y por tanto dinero al tener una comunicación directa 
* Reducimos dependencias

### Consecuencias negativas

* Muchos costes de mantenimiento de esta comunicación

## Pros y contras de las opciones

### Tener una comunicación directa con banco central que gestione y valide la compra.

* Bueno, porque nos da versatilidad e independencia a la hora de hacer crecer nuestra aplicación.
* Malo, porque engrosa los costes al tener que crear esa comunicación y mantenerla.
* Malo, porque engrosa también los costes de crecimiento del microservicio de compras.

### Gestionar la validación de los pagos desde un plugin o un módulo externo a nuestra aplicación.

* Bueno, porque nos permite gastar tiempo en otros recursos de la aplicación.
* Malo, porque dependemos de una empresa a parte para nuestro sistema, lo que puede traer consigo problemas.
* Malo, porque el coste se mantiene en el tiempo aunque sea más barato en un inicio.








