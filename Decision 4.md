# Decisión sobre la coherencia entre las distintas bases de datos

* Estado: Propuesta
* Decisores: Alejandro Fernández San Román
* Fecha: 2022/04/14

Descripción técnica: Se necesita que exista coherencia entre las distintas bases de datos

## Contexto y declaración del problema

La aplicación tiene que ser segura en compras

## Motivos de la decision 

* RF3 Coherencia entre las bases de datos

## Opciones consideradas

* Gestionar la coherencia entre las bases de datos manualmente a través de un nuevo módulo en la capa de negocio.
* Gestionar la coherencia entre las bases de datos a traves de un sistema de mensajería como RabbitMQ.
* Gestionar la coherencia entre las bases de datos a través de un bus dedicado como Azure Service Bus. 

## Resultado de la decisión

Opción escogida: "Gestionar la coherencia entre las bases de datos a traves de un sistema de mensajería como RabbitMQ", .

### Consecuencias positivas

* X

### Consecuencias negativas

* X

## Pros y contras de las opciones

### Gestionar la coherencia entre las bases de datos manualmente a través de un nuevo módulo en la capa de negocio

* Bueno, porque nos permite centralizar los problemas y no depender de tecnologías externas.
* Malo, porque hace más costosa la produccion y el desarrollo de la aplicaión.
* Malo, porque hace más susceptible a bugs a la aplicación.

### Gestionar la coherencia entre las bases de datos a traves de un sistema de mensajería como RabbitMQ

* Bueno, integrado junto con Docker y Kubernetes es el sistema más portable para diferentes infraestructuras.
* Malo, existen reportes de fallos de persistencia y escalabilidad en relación con RabbitMQ.

### Gestionar la coherencia entre las bases de datos a través de un bus dedicado como Azure Service Bus

* Bueno, porque disponemos de la seguridad de tener a una empresa como Microsoft de proveedor de servicios.
* Bueno, porque es una tecnología muy demandada actualmente y por ello el soporte está más activo.
* Malo, porque nos brinda de menor escalabilidad.
