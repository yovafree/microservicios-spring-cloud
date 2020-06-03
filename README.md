# Proyecto Ejemplo de Spring Cloud

Un proyecto de ejemplo que demuestra una plataforma nativa de nube de extremo a extremo que usa Spring Cloud para construir una arquitectura práctica de microservicios.

Conceptos demostrados:

* Pruebas de integración con Docker
* Persistencia políglota
* Arquitectura de microservicios
* Service discovery
* API gateway

## Docker

Cada servicio se construye e implementa con Docker. Las pruebas de integración de extremo a extremo se pueden realizar en la máquina de un desarrollador utilizando Docker compose.

## Persistencia políglota

Uno de los conceptos centrales de este proyecto de ejemplo es cómo se puede abordar la persistencia políglota en la práctica. Los microservicios en el proyecto usan su propia base de datos, mientras se integran con los datos de otros servicios a través de REST o un bus de mensajes.

* Neo4j (graph)
* MongoDB (Documento)
* MySQL (Relacional)

## Recomendaciones de películas

Este proyecto de ejemplo se centra en películas y recomendaciones.

### Servicio de Datos

![http://i.imgur.com/NXLHvjR.png](http://i.imgur.com/NXLHvjR.png)

### Datos de dominio

![http://i.imgur.com/VlwSw2q.png](http://i.imgur.com/VlwSw2q.png)

## Arquitectura de microservicios

Este proyecto de ejemplo muestra cómo construir una nueva aplicación utilizando microservicios, en oposición a una estrategia de monolito. Ya que cada microservicio en el proyecto es un módulo de un único proyecto principal, los desarrolladores tienen la ventaja de poder ejecutar y desarrollar con cada microservicio localmente en su máquina. Agregar un nuevo microservicio es fácil, ya que el microservicio de descubrimiento, encontrará automáticamente nuevos servicios que se ejecutan en el clúster.

## Service discovery

Este proyecto contiene dos servicios de descubrimiento, uno en Netflix Eureka y el otro utiliza Consul de Hashicorp. Tener múltiples servicios de descubrimiento brinda la oportunidad de usar uno (Consul) como proveedor de DNS para el clúster y el otro (Eureka) como una puerta de enlace API basada en proxy.

## API gateway

Cada microservicio se coordinará con Eureka para recuperar rutas API para todo el clúster. Con esta estrategia, cada microservicio en un clúster puede equilibrarse en la carga y exponerse a través de una puerta de enlace API. Cada servicio descubrirá y enrutará automáticamente las solicitudes de API al servicio que posee la ruta. Esta técnica de proxy es igualmente útil cuando se desarrollan interfaces de usuario, ya que la API completa de la plataforma está disponible a través de su propio host como proxy.

# Licencia

Este proyecto es un producto de código abierto con licencia bajo GPLv3.
