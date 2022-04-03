# Decisión sobre el estilo arquitectónico

* Estado: propuesto
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

Opción escogida: "{option n}", porque {justificación, escoger solo una opción que resuelve el problema}.

### Consecuencias positivas <!-- opcional -->

* {consecuencia 1}
* …

### Consecuencias negativas <!-- opcional -->

* {e.g., compromising quality attribute, follow-up decisions required, …}
* …

## Pros y contras de las opciones

### Dividir en microservicios solo la capa de negocio

* Bueno, porque requiere menos trabajo y por ende menos costes.
* Bueno, porque no tenemos que portar las bases de datos ni la interfaz del usuario, el funcionamiento general de la aplicación se mantendría intacto.
* Malo, porque es menos escalable y más susceptible de problemas generales que afecten a toda la aplicación.

### Dividir toda la aplicación previa en distintos microservicios


* Bueno, porque permite gestionar los fallos para que solo afecten a una parte concreta de la aplicación.
* Bueno, porque ayuda a futuro a escalar mejor la aplicación fuera de la lógica de negocio.
* Malo, porque requiere más trabajo y por ende, más costes.








