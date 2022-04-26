# Decisión sobre los distintos módulos de la aplicación

* Estado: Finalizada
* Decisores: Alejandro Fernández San Román
* Fecha: 2022/04/05

Descripción técnica: Decisión sobre el módulo de seguridad de la aplicación

## Contexto y declaración del problema

La aplicación tiene que ser segura en compras

## Motivos de la decision 

* RF2.4 Módulo de seguridad

## Opciones consideradas

* Implementar un sistema de hash para la autenticidad del sistema así como un sistema de logs para mantener la trazabilidad dentro del módulo de compras
* Utilización de un sistema de doble verificación del usuario cuando vas a realizar la compra
* Utilizar ambas cosas

## Resultado de la decisión

Opción escogida: "Utilizar ambas cosas", porque así conseguimos mayor seguridad con respecto a la autenticidad de nuestros usuarios.

### Consecuencias neutras

* Se tendrá una clase en el microservico de compras encargada de hashear las compras.
* El usuario tendrá un numero de telefono al cual verificar la compra que se está haciendo.
* Una clase adicional en el microservicios de pedidos y compras gestionará el mensaje al usuario a través de su numero de telefono y un metodo que genera y verifica un numero aleatorio.

### Consecuencias positivas

* La seguridad de nuestro sistema aumentaría más que si implementaramos solo un sistema de hash o un sistema de doble verificación.

### Consecuencias negativas

* Tendríamos más elementos que mantener, por lo que los costes aumentarían.

## Pros y contras de las opciones

### Implementar un sistema de hash para la autenticidad del sistema así como un sistema de logs para mantener la trazabilidad dentro del módulo de compras

* Bueno, porque nos permite mediante una función simple saber quien es quien está entrando, así como mantener seguros los datos una vez dentro de nuestro sistema.
* Bueno, porque encriptar datos, usando SHA-256 p.E. no es algo caro ni dificil de implementar.
* Bueno, porque los logs son un sistema simple, barato y eficiente de tener un registro de todo lo que ocurre en tu aplicación.
* Malo, porque almacenar todos los logs es muy caro y irlos borrando los hace inútiles a largo plazo.
* Malo, porque si se utilizan hash como llave pero no se encripta los elementos, solo tenemos autenticidad dentro de la seguridad, pero no tenemos confidencialidad de los datos.

### Utilización de un sistema de doble verificación del usuario cuando vas a realizar la compra


* Bueno, porque nos asegura confidencialidad de los datos, solo prodrá acceder a los datos la persona que queremos que acceda.
* Bueno, porque aumenta la seguridad también en el cliente para que realice compras más frecuentemente a sabiendas que no hay fallos de seguridad en su cuenta.
* Malo, porque porque es más caro y requiere de una aplicación a parte o de terceros para la doble autenticación, ya sea una palicación de movil o de escritorio.

### Utilizar ambas cosas


* Bueno, porque aumenta enormemente la seguridad a la hora de comprar.
* Malo, porque engrosa mucho los costes de la aplciación.








