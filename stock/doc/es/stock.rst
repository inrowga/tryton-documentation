=========
Logística
=========

.. inheritref:: stock/stock:section:configuracion

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

Los |out_state| de un albarán de cliente són:

* Borrador
* Realizado
* Cancelado
* Asignado
* Empaquetado
* En espera

En el caso que realizemos un albarán de cliente de devolución es similar al
de salida pero en vez de salir productos, los volveremos a nuestro almacén.
La gestión de estos albaranes lo haremos a |menu_shipment_out_return_form|.

.. |menu_shipment_out_return_form| tryref:: stock.menu_shipment_out_return_form/complete_name
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

.. inheritref:: stock/stock:section:movimientos

Movimientos
===========

Los albaranes de salida, entrada o internos crean movimientos. El listado de todos
los movimientos los podemos consultar a |menu_move_form|.

.. |menu_move_form| tryref:: stock.menu_move_form/complete_name
