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
