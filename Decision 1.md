# Decisión sobre el estilo arquitectónico

* Estado: Aceptado
* Decisores: Alejandro Fernández San Román
* Fecha: 2022/04/02

Descripción técnica: Decisión sobre el estilo arquitectónico que la aplicación tendrá

## Contexto y declaración del problema

Se necesita un estilo arquitectónico del que partir para, desde ahí, empezar a construir la aplicación.

## Motivos de la decision 

* RF1 Migración de la arquitectura
* RF2 Módulos de negocio

## Opciones consideradas

* Partiendo del estilo por capas del que procedemos, dividir solamente la capa de negocio en microservicios y mantener las capas de bases de datos y de usuario
* Dividir todas las funcionalidades de el previo estilo por capas en distintos microservicios

## Resultado de la decisión

Opción escogida: "Dividir en microservicios solo la capa de negocio", porque al no tener que dividir todas las capas en microservicios, requiere menos trabajo y tanto la base de datos como la interfaz de usuario se mantendrían igual.

### Consecuencias positivas <!-- opcional -->

* Ayudará a que toda la aplicación esté más centralizada.
* Cada vez que se añada un mocroservicio, este contará con su enlace pertinente a la base de datos donde se almacene su localización.

### Consecuencias negativas <!-- opcional -->

* Será difícil añadir funcionalidades fuera de la capa de negocios, disminuyendo así la escalabilidad.

## Pros y contras de las opciones

### Dividir en microservicios solo la capa de negocio

* Bueno, porque requiere menos trabajo y por ende menos costes.
* Bueno, porque no tenemos que portar las bases de datos ni la interfaz del usuario, el funcionamiento general de la aplicación se mantendría intacto.
* Malo, porque es menos escalable y más susceptible de problemas generales que afecten a toda la aplicación.

### Dividir toda la aplicación previa en distintos microservicios


* Bueno, porque permite gestionar los fallos para que solo afecten a una parte concreta de la aplicación.
* Bueno, porque ayuda a futuro a escalar mejor la aplicación fuera de la lógica de negocio.
* Malo, porque requiere más trabajo y por ende, más costes.








