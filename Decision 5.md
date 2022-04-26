# Decisión sobre la limitación de intentos de compra

* Estado: Finalizada
* Decisores: Alejandro Fernandez San Roman, Gabriel Fuentes Villasevil 
* Fecha: 2022-04-20 

Descripción técnica: Decisión sobre la limitación de intentos de compra, que deberá ser de 5

## Contexto y declaración del problema

La aplicación una vez esté en funcionamiento una gran cantidad de peticiones de intento de compra simultaneos podría causar errores en el sistema.

## Motivos de la decision 

* RF 1.3 Microservicio pedidos y compras

## Opciones consideradas

* Añadir un contador de intentos de compra a cada usuario.
* Crear una clase limitante, que gestione todas las peticiones de todos los usuarios.

## Resultado de la decisión

Opción escogida: "Crear una clase limitante, que gestione todas las peticiones de todos los usuarios.", porque nos permite tener un contador que disminuya la probabilidad de error y no rompemos ninguna idea.

### Consecuencias positivas <!-- opcional -->

* Conseguimos ahorrar espacio en la base de datos
* Si hay algún fallo este no se propagará

### Consecuencias negativas <!-- opcional -->

* Pueden producirse tiempos de espera innecesarios
* Complejidad de testing

## Pros y contras de las opciones <!-- opcional -->

### Añadir un contador de intentos de compra a cada usuario.

* Bueno, porque es simple de implementar, y permite que no se sobrecargue el número de peticiones a los microservicios correspondientes.
* Malo, porque en caso de fallo en la información detallada en el usuario éste podría saltarse la restricción.
* Malo, porque rompe con la idea de que la clase usuario tenga única y exclusivamente datos propios que se guardaran en la base de datos, por lo que usaremos memoria de más.

### Crear una clase limitante, que gestione todas las peticiones de todos los usuarios.

* Bueno, porque la información almacenada en esta clase no tendria porqué almacenarse en las bases de datos, liberando memoria.
* Bueno, porque aunque un usuario tenga un fallo en su información el fallo no se propaga, evitando que se salte la limitación.
* Malo, porque su implementación es más compleja.
