<h1>DAS_JUNIO</h1>

<h2>REQUISITOS</h2>
<table style="width: 100%; text-align: center;">
  <tr>
    <td style="width: 33%;">Nº DEL REQUISITO</td>
    <td style="width: 33%;">NOMBRE</td>
    <td style="width: 33%;">DESCRIPCIÓN</td>
  </tr>
  <tr>
    <td style="width: 33%;">1</td>
    <td style="width: 33%;">Migración de la arquitectura</td>
    <td style="width: 33%;">Se desea migrar la antigua capa de negocio a una basada en microservicios más escalables y flexibles, éstos se deben poder integrar en la aplicación de forma asíncrona y se debe de almacenar la dirección del microservicio en una BBDD MongoDB para poder acceder a ellos en todo momento. El sistema contendrá los siguientes microservicios:</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF1.2</td>
    <td style="width: 33%;">Microservicio preferencias</td>
    <td style="width: 33%;">Es necesario que un microservicio almacene las preferencias de los usuarios, almacenando los artículos que compra, el nombre del usuario, y el precio que ha pagado por el artículo en cuestión, éstos datos se almacenarán en una base de datos NoSQL ya existente.</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF1.3</td>
    <td style="width: 33%;">Microservicio pedidos y compras</td>
    <td style="width: 33%;">Es necesario un microservicio dedicado a que el usuario haga pedidos y compras, éstos se gestionan gracias al id del producto y del cliente que compra, éstas se deben de almacenar en una BBDD SQL a través de un bus de eventos lógicos, y se debe impedir al usuario intentar comprar más de 5 veces.</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF1.4</td>
    <td style="width: 33%;">Comunicación de microservicios</td>
    <td style="width: 33%;">Los microservicios han de comunicarse entre ellos usando el protocolo REST, así como comunicarse con los elementos fuera del sistema a través de un gateway que debe soportar comunicaciones HTTP</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF1.5</td>
    <td style="width: 33%;">Microservicio de devoluciones</td>
    <td style="width: 33%;">Se desea que el usuario pueda realizar una devolución de una compra a través de un microservicio, éste se debe de comunicar con el microservicio de compras para verificar que la devolución pertenece a las compras realizadas.</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF2</td>
    <td style="width: 33%;">Módulos de negocio</td>
    <td style="width: 33%;">La aplicación que migramos se divide en distintos módulos que se han de mantener, los cuales son:</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF2.2</td>
    <td style="width: 33%;">Módulo de pagos</td>
    <td style="width: 33%;">El sistema debe de gestionar los pagos realizados por nuestros clientes desde el microservicio de compras, que lo valide para que ésta se realice con éxito.</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF2.3</td>
    <td style="width: 33%;">Módulo de mensajería</td>
    <td style="width: 33%;">El sistema debe tener un módulo de mensajería como una capa horizontal debajo de la capa de negocio, soportado por un middleware independiente, que usará el protocolo de AMQP.</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF2.4</td>
    <td style="width: 33%;">Módulo de seguridad</td>
    <td style="width: 33%;">Es necesario que exista un módulo de seguridad en compras.</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF3</td>
    <td style="width: 33%;">Middleware de mensajería</td>
    <td style="width: 33%;">El sistema de mensajería se soporta por un middleware externo a nuestro sistema.</td>
  </tr>
  <tr>
    <td style="width: 33%;">RF4</td>
    <td style="width: 33%;">Coherencia entre las bases de datos.</td>
    <td style="width: 33%;">La coherencia entre las distintas bases de datos se certificará mediante a través de un bus de eventos lógicos. El cliente sugiere que utilicen tecnología de mensajería como RabbitMQ o un “bus” dedicado como Azure Service Bus.</td>
  </tr>
</table>

