# MongoDB_estructura

Este proyecto consiste en la creación de una base de datos para la óptica “Cul d’Ampolla”, utilizando MongoDB Compass.
El objetivo es informatizar la gestión de clientes, gafas, proveedores, empleados y ventas, manteniendo relaciones entre ellos.
Base de datos: optica

Colecciones incluidas:

clientes

proveedores

gafas

empleados

ventas
📂 Descripción de las colecciones
🧍‍♀️ clientes

Contiene la información personal y de contacto de los clientes.
Campos principales:

nombre, direccion, telefono, email, fecha_registro

recomendador_id: referencia al_id de otro cliente que lo recomendó

👉 Relación: auto-relación entre clientes mediante $lookup (recomendador → recomendado)

🕶️ gafas

Contiene los modelos de gafas disponibles.
Campos principales:

marca, graduacion, montura, color_montura, color_vidrio, precio

proveedor_id: referencia al_id de la colección proveedores

👉 Relación: gafas → proveedores

🏭 proveedores

Información de los proveedores de las gafas.
Campos:

nombre, direccion, telefono, fax, nif, pais

👩‍💼 empleados

Datos de los empleados que realizan las ventas.
Campos:

nombre, telefono, email, cargo

💰 ventas

Registra las operaciones de venta.
Campos:

cliente_id: referencia a clientes._id

gafa_id: referencia a gafas._id

empleado_id: referencia a empleados._id

fecha_hora: fecha y hora de la venta

👉 Relación múltiple: ventas → clientes, ventas → gafas, ventas → empleados

🔗 Relaciones entre colecciones (usando $lookup)

Cada colección se ha creado e importado en formato JSON

🧰 Herramientas utilizadas

MongoDB Compass para modelado, importación y relaciones.

JSON como formato de intercambio de datos.

$lookup.
