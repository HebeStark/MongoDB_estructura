# ## Modelado NoSQL con MongoDB - Óptica Cul d’Ampolla

-Objetivo del ejercicio

Aprender a modelar bases de datos NoSQL utilizando MongoDB, diseñando la estructura en función de los patrones de consulta y del punto de vista de la interfaz gráfica.

Se prioriza la estructura orientada a la vista principal.

Pero se mantienen todas las entidades del dominio (clientes, gafas, empleados, proveedores y ventas como concepto).

## Ejercicio 1 — Vista centrada en el Cliente

La interfaz muestra:
-Datos personales del cliente
-Últimas compras realizadas
-Detalles de cada gafa adquirida
-Empleado que realizó la venta

## Decisión de modelado

Se aplica un modelo embebido orientado a consulta, almacenando las compras dentro del documento clientes.
Como la vista siempre muestra cliente + compras, estas se almacenan embebidas.
Sin embargo:
Se mantienen las colecciones de gafas, empleados y proveedores como parte del dominio.
La entidad ventas sigue existiendo conceptualmente, aunque en esta versión se representa como subdocumento embebido.

## Diagrama — Vista Cliente

Archivo:
vista_cliente.drawio.png

El diagrama representa:

Documento principal:
-clientes
-Array compras[] embebido
Dentro de compras:
-empleado embebido
-gafas embebidas
Colección proveedores independiente

## Ejercicio 2 — Vista centrada en las Gafas

La interfaz muestra:
-Datos de una gafa
-Información del proveedor
-Clientes que la han comprado
-Empleado que realizó cada venta

## Decisión de modelado2

Se diseña un modelo alternativo embebido, donde las ventas se almacenan dentro del documento gafas.
El principio aplicado es el mismo:
El diseño depende del punto de vista de la consulta.
En esta versión:
Se prioriza la lectura desde la colección gafas.
Las ventas se embeben dentro del documento producto.
Se mantienen las entidades clientes, empleados y proveedores como parte del dominio global.

## Diagrama — Vista Gafas

Archivo:
vista_gafas.drawio.png

El diagrama representa:

Documento principal:
-gafas
-Subdocumento proveedor
-Array ventas[]
-cliente embebido
-empleado embebido
