# MongoDB_estructura

Para el análisis y validación de la estructura de las colecciones he utilizado MongoDB Compass, quw me permite visualizar campos y tipos de datos reales almacenados en cada colección.
A partir de esta visualización he elaborado un diagrama conceptual en el que se representan las relaciones entre colecciones.

Colecciones incluidas:
-clientes

Almacena la información personal de los clientes de la óptica:
Nombre
Dirección postal (embebida como objeto)
Teléfono
Correo electrónico
Fecha de registro
Cliente que lo ha recomendado (autoreferencia opcional)
Las compras no se almacenan en clientes, sino en colección ventas.

-proveedores

Contiene los datos de los proveedores de gafas:
Nombre
Sirección completa (calle, número, ciudad, código postal y país)
Teléfono
Fax
NIF
La dirección se enbebe como objeto para facilitar consultas por localización.

-gafas

Representra los productos que vende la óptica:
Marca
Graduación de cada vidrio
Tipo y color de montura
Coloor de cada vidrio
Precio
Proveedor (referencia a proveedores)
Cada gafa pertenece a un único proveedor, modelado mediante una referencia (ObjectId).

-empleados

Alamcena la información del personal de la óptica:
Nombre
Teléfono
Correo electrónico
Cargo
Los empleados no almacenan ventas, ya que estas se getionan desde la colección ventas.

-ventas

Es la colleción central del sistema y representa cada operación de venta:
Cliente que la realiza
Fecha y hora de la venta
Lista de gafas vendidas (array embebido)
Esta estructura permite responder a todas las consultas del sistema sin duplicar información


## Relaciones entre collecciones

Un cliente puede realizar muchas compras

Un empleado puede gestionar muchas ventas

Una venta pertenece a un único cliente y a un único empleado

Una venta puede incluir  una o varias gafas

Cada gafa pertenece a un ùnico proveedor

Las relaciones se implementan mediante referencias (ObjectId), para evitar duplicidad de datos.

## Descripción de diseño

Se utilizan documentos embebidos para estructuras que dependen directamente del documento principal (direcciones, graduaciones, vidrios).

Se han utilizado referencias para relaciones entre entidades independientes (clientes, empleados, proveedores).

-Las ventas centralizan la información transaccional.

-Los datos se entregan en formato JSON.

## Ejercicio 2

Punto de vista centrado en las gafas:
En este segundo ejercicio, el punto de vista de la interfaz se centra en las gafas, mostrando su información y los clientes que las han comprado.
El modelo de datos no necesita ser modificado, ya que la colección 'ventas' centraliza la información transaccional y permite obtener facilmente los clientes asociados a una gafa concreta mediante consultas.



