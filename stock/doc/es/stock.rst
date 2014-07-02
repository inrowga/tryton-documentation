=========
Logística
=========

.. inheritref:: stock/stock:section:ubicaciones

Ubicaciones
===========

Las ubicaciones nos permiten especificar los almacenes o lugares físicos o virtuales
de nuestros productos.

Para gestionar las ubicaciones accederemos a |menu_conf_location|.

.. |menu_conf_location| tryref:: stock.menu_location_form/complete_name

* |loc_name|
* |loc_code|
* |loc_active|
* |loc_address|
* |loc_type|
* |loc_parent|
* |loc_input_location|
* |loc_storage_location|

Las opciones del |loc_type| de ubicación son:

* Proveedor
* Cliente
* Perdido/Encontrado
* Almacén
* Interna
* Producción

.. |loc_name| field:: stock.location/name
.. |loc_code| field:: stock.location/code
.. |loc_active| field:: stock.location/active
.. |loc_address| field:: stock.location/address
.. |loc_type| field:: stock.location/type
.. |loc_parent| field:: stock.location/parent
.. |loc_input_location| field:: stock.location/input_location
.. |loc_storage_location| field:: stock.location/storage_location

.. inheritref:: stock/stock:section:albaranes

Albaranes
=========

Para crear o listar los albaranes accederemos a los menús:

* |menu_shipment_in_form|: Para albaranes de entrada.
* |menu_shipment_out_form|: Para albaranes de salida.
* |menu_shipment_internal_form|: Para albaranes internos.

.. |menu_shipment_in_form| tryref:: stock.menu_shipment_in_form/complete_name
.. |menu_shipment_out_form| tryref:: stock.menu_shipment_out_form/complete_name
.. |menu_shipment_internal_form| tryref:: stock.menu_shipment_internal_form/complete_name

.. inheritref:: stock/stock:section:albaranes_de_proveedor

Albaranes de proveedor
----------------------

Un albaran de proveedor es un albarán de entrada que nos incrementará nuestro
stock en los productos.

* |in_effective_date|
* |in_planned_date|
* |in_reference|
* |in_supplier|
* |in_supplier_location|
* |in_contact_address|
* |in_warehouse|
* |in_moves|
* |in_code|
* |in_state|

Los |in_state| de un albarán de proveedor són:

* Borrador
* Recibidos
* Realizado
* Cancelado

En el caso que realizemos un albarán de proveedor de devolución es similar al
de entrada pero en vez de recibir productos, los devolvemos. La gestión de estos
albaranes lo haremos a |menu_shipment_in_return_form|.

.. |menu_shipment_in_return_form| tryref:: stock.menu_shipment_in_return_form/complete_name
.. |in_effective_date| field:: stock.shipment.in/effective_date
.. |in_planned_date| field:: stock.shipment.in/planned_date
.. |in_reference| field:: stock.shipment.in/reference
.. |in_supplier| field:: stock.shipment.in/supplier
.. |in_supplier_location| field:: stock.shipment.in/supplier_location
.. |in_contact_address| field:: stock.shipment.in/contact_address
.. |in_warehouse| field:: stock.shipment.in/warehouse
.. |in_moves| field:: stock.shipment.in/moves
.. |in_code| field:: stock.shipment.in/code
.. |in_state| field:: stock.shipment.in/state

.. inheritref:: stock/stock:section:albaranes_de_cliente

Albaranes de cliente
---------------------

Un albaran de cliente es un albarán de salida que nos disminuirá nuestro
stock en los productos.

* |out_effective_date|
* |out_planned_date|
* |out_customer|
* |out_customer_location|
* |out_delivery_address|
* |out_reference|
* |out_warehouse|
* |out_moves|
* |out_code|
* |out_state|

Los albaranes de cliente están formados por dos tipos de movimiento:

* |out_inventory_moves|: Son aquellos movimientos en que cojemos los
  productos de su ubicación actual (dónde se almacenan) y los preparamos para
  entregarlos al cliente.
* |out_outgoing_moves|: Movimientos que representan la entrega real al
  cliente.

.. |out_effective_date| field:: stock.shipment.out/effective_date
.. |out_planned_date| field:: stock.shipment.out/planned_date
.. |out_customer| field:: stock.shipment.out/customer
.. |out_customer_location| field:: stock.shipment.out/customer_location
.. |out_delivery_address| field:: stock.shipment.out/delivery_address
.. |out_reference| field:: stock.shipment.out/reference
.. |out_warehouse| field:: stock.shipment.out/warehouse
.. |out_moves| field:: stock.shipment.out/moves
.. |out_code| field:: stock.shipment.out/code
.. |out_state| field:: stock.shipment.out/state
.. |out_inventory_moves| field:: stock.shipment.out/inventory_moves
.. |out_outgoing_moves| field:: stock.shipment.out/outgoing_moves

Un albarán de cliente puede estar en alguno de los siguientes estados.

* **Borrador**: Estado inicial en que se introducen los movimientos de salida
  previstos.
* **En espera**: El albarán contiene los movimientos de salida y los
  movimientos de inventario previstos, ambos en estado borrador.
* **Asignado**: Todos los movimientos movimientos de inventario hay sido
  reservados aunque no realizados.
* **Empaquetado**: Todos los movimientos movimientos de inventario han sido ya
  realizados y el albarán está a la espera de ser entregado al cliente.
* **Realizado**: El albarán esta completamente realizado y los productos han
  sido enviados al cliente.
* **Cancelado**: El albarán ha sido cancelado.

Flujo de albaranes de cliente
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

El primer paso para crear un albarán, es crear sus movimientos de salida.
Una vez creados, podemos utilizar el botón En espera para crear los
movimientos de inventario, automàticamente se nos crearán los movimientos de
inventario necesarios para satisfacer los movimientos de salida.

Al pulsar el botón Reservar el sistema intentará asignar todos los movimientos
de inventario, teniendo en cuenta el stock del almacén.

En caso de que no haya suficiente stock en el almacén para satisfacer todos
los movimientos de inventario, el sistema nos mostrará el siguiente aviso:

.. figure:: images/unable-to-assign-moves.png

Dónde podremos visualizar de cada producto las cantidades que no se pueden
reservar (porqué no hay suficiente estoc), junto con sus cantidades. El botóni
Forzar reserva nos permitirá asignar igualmente los movimientos, però sólo nos
aparecerá en caso de que nuestro usuario pertenezca al grupo
|group_stock_force|. También podemos aceptar el aviso con el botón Aceptar.

.. |group_stock_force| tryref:: stock.group_stock_force_assignment/name

En caso de que no hayamos forzado las reservas, el albarán quedará en estado
en espera, con los movimientos que se hayan podido reservar en estado
Reservado, y los movimientos pendientes de reservar en estado Borrador.
Podemos cancelar las reservas parciales, utilizando el botón En espera.
Una vez asignados los movimientos de estoc, podemos utilizar el botón
Realizar envió para marcar el envío cómo empaquetado.
Los movimientos de inventario estarán completamente realizados, però los
movimientos de salida estarán reservados, a la espera de ser entregados al
cliente. Una vez entregado al cliente, podemos marcar el albarán cómo
realizado con el botón Realizado.


En el caso que realizemos un albarán de cliente de devolución es similar al
de salida pero en vez de salir productos, los volveremos a nuestro almacén.
La gestión de estos albaranes lo haremos a |menu_shipment_out_return_form|.

.. |menu_shipment_out_return_form| tryref:: stock.menu_shipment_out_return_form/complete_name

.. inheritref:: stock/stock:section:albaranes_internos

Albaranes internos
------------------

Un albaran de interno no es un albarán ni de entrada ni de salida. Es un albarán
que contine productos para un cambio de ubicación dentro de nuestra empresa.

* |internal_effective_date|
* |internal_planned_date|
* |internal_code|
* |internal_reference|
* |internal_from_location|
* |internal_to_location|
* |internal_moves|
* |internal_state|

Los |internal_state| de un albarán de cliente són:

* Borrador
* Cancelado
* Asignado
* En espera
* Realizado

.. |internal_effective_date| field:: stock.shipment.internal/effective_date
.. |internal_planned_date| field:: stock.shipment.internal/planned_date
.. |internal_code| field:: stock.shipment.internal/code
.. |internal_reference| field:: stock.shipment.internal/reference
.. |internal_from_location| field:: stock.shipment.internal/from_location
.. |internal_to_location| field:: stock.shipment.internal/to_location
.. |internal_moves| field:: stock.shipment.internal/moves
.. |internal_state| field:: stock.shipment.internal/state

Cancelar albaranes
------------------

En cualquier momento del flujo podremos cancelar los albaranes. Cancelar un
albarán implica cancelar todos los movimientos (tanto los de inventario como
los de entrada/salida) que están en estado borrador o reservado. Los
movimientos que ya están realizados **no se pueden cancelar**.

En caso de que ya hayamos realizado los movimientos de inventario y necesitemos
cancelar el albarán, deberemos crear manualmente un albarán interno para
devolver los productos de la zona de recepción del cliente a la zona de
almacenamiento de nuevo.

Una vez cancelado un albarán este puede volver a estado borrador utilizando
el botón Borrador.


.. inheritref:: stock/stock:section:movimientos

Movimientos
===========

Los albaranes de salida, entrada o internos crean movimientos. El listado de todos
los movimientos los podemos consultar a |menu_move_form|.

.. |menu_move_form| tryref:: stock.menu_move_form/complete_name

Stock o cantidad de los productos
=================================

Para saber la cantidad de un producto debemos primero filtrar los productos por
ubicación. A |menu_location_tree| escojaremos la ubicación y seleccionamos la fecha
(por defecto la fecha es a día de hoy). En la siguiente ventana dispondremos de todos
los productos por esta ubicación y con la cantidad a día de hoy.

.. |menu_location_tree| tryref:: stock.menu_location_tree/complete_name

.. inheritref:: stock/stock:section:configuracion

Inventario
==========

La creación de un inventario le permite regularizar el stock o las cantidades de los
productos. A |menu_inventory_form| podrá generar los inventarios.

Para la generación de un inventario deberemos seleccionar:

* Ubicación donde hacemos el inventario
* Ubicación "Perdido/encontrado"
* Líneas. Cada línea corresponde a un producto y la cantidad que se dispone de este producto.

En el momento de procesar el inventario se nos crearán los movimientos (uno por cada producto),
de la ubicación por ejemplo "Perdido/encontrado" a la ubicación por ejemplo "Zona de almacenamiento".

Para consultar todos los movimientos que se han realizado accede a |menu_move_form|. Los movimientos
ya se encuentran en estado realizado.

Inventario completo
-------------------

Al hacer un inventario disponemos de la acción de cargar todos los productos de nuestro
sistema con la cantidad que disponemos en la ubicación. Esta acción puede ser útil
si realizamos el inventario anual donde debemos procesar todos los productos.

En el momento de procesar el inventario, por cada línea se nos creará un nuevo movimiento.

El tiempo de carga de esta acción en las líneas del inventario dependerá de la
cantidad de productos que disponemos.

.. |menu_inventory_form| tryref:: stock.menu_inventory_form/complete_name
.. |menu_move_form| tryref:: stock.menu_move_form/complete_name

Cantidad estimada
-----------------

Es importante cuando realice un inventario disponer de la cantidad estimada por
cada línea del inventario. La cantidad estimada es la cantidad actual en el almacén.
Esta opción evita en el momento de hacer un inventario tener conflictos de stock si
al mismo momento se realizan ventas o compras.

Según la cantidad estimada y la cantidad que introduce en la línea del inventario, se
suma a partir de la cantidad que se disponga. Es importante que si la cantidad estimada
es un valor negativo, recalcular la cantidad estimada y no sea 0.

Configuración
=============

A |menu_configuration| nos permite:

.. |menu_configuration| tryref:: stock.menu_stock_configuration/complete_name

* |shipment_in_sequence|
* |shipment_in_return_sequence|
* |shipment_out_sequence|
* |shipment_out_return_sequence|
* |shipment_internal_sequence|

.. |shipment_in_sequence| field:: stock.configuration/shipment_in_sequence
.. |shipment_in_return_sequence| field:: stock.configuration/shipment_in_return_sequence
.. |shipment_out_sequence| field:: stock.configuration/shipment_out_sequence
.. |shipment_out_return_sequence| field:: stock.configuration/shipment_out_return_sequence
.. |shipment_internal_sequence| field:: stock.configuration/shipment_internal_sequence
