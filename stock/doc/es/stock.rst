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

.. inheritref:: stock/stock:section:recepcion_mercaderia

Recepción de mercaderia
=======================

Para recibir mercadería debemos crear un albarán de proveedor desde la opción
|menu_shipment_in_form|.

Un albarán de proveedor es un albarán de entrada que nos incrementará las
cantidades de productos en nuestros almacenes.
Los albaranes de proveedor están formados por dos tipos de movimiento:

* |in_incoming_moves|: Movimientos que representan la recepción real del
  proveedor.
* |in_inventory_moves|: Son aquellos movimientos en que almacenamos los
  productos recibidos en su ubicación en el almacén.

Un albarán de proveedor puede estar en alguno de los siguientes estados:

* **Borrador**: Estado inicial en que se introducen los movimientos que
  recibimos.
* **Recibido**: Hemos recibido la mercadería del |in_supplier| pero aún no
  ha sido almacenada en nuestros almacenes.
* **Realizado**: La mercadería ha sido recibida y almacenada en nuestros
  almacenes.
* **Cancelado**: El albarán ha sido cancelado.

Para crear uno deberemos introducir el |in_supplier| y el |in_warehouse|.
En este momento ya podremos introducir todos los |in_incoming_moves|, para
especificar los productos que estamos recibiendo. Una vez introducidos todos
los movimientos, pulsamos sobre el botón Recibir para realizar todos los
|in_incoming_moves|. Una vez realizados, el sistema nos rellenará los
|in_inventory_moves|, pudiéndolos modificar para especificar en que ubicación,
los queremos almacenar. Una vez especificada podemos finalizar la recepción
mediante el botón Realizado.

Introducción de albaranes ya realizados
---------------------------------------

En caso de que debemos introducir la recepción de una mercadería que se haya
realizado en el pasado, podemos introducir una fecha en el campo
|in_effective_date|, para indicar la fecha en que se realizó la recepción.
Así todos los productos nos aparecerán disponibles en el listado de estoc a
partir de la fecha que indiquemos.

Devolución de mercadería
------------------------

Para devolver mercadería debemos crear un albarán de devolución de proveedor
desde la opción |menu_shipment_in_return_form|.

Un albarán de devolución proveedor puede estar en alguno de los siguientes
estados:

* **Borrador**: Estado inicial en que se introducen los movimientos que
  vamos a devolver.
* **Esperando**: A la espera que la mercadería este disponible en la ubicación
  desde dónde la vamos a enviar.
* **Reservado**: Todos los movimientos han sido reservados para que se puedan
  enviar al proveedor.
* **Realizado**: La mercadería ha sido entregada al proveedor.
* **Cancelado**: El albarán ha sido cancelado.

Para crear un albarán de devolución a proveedor debemos introducir la ubicación
desde dónde vamos a devolver los productos en el campo |in_return_form_location|
y la ubicación dónde vamos a enviar los productos en el campo
|in_return_to_location|. Una vez introducidos podemos introducir los
|in_return_moves|. Una vez introducidos, utilizaremos el botón Esperando, para
indicar que estamos a la espera de la mercadería. Si necesitamos realizar
alguna modificación en el albarán, siempre podemos volver al estado borrador.

En caso de que no haya suficiente stock en la ubicación para satisfacer todos
los movimientos, el sistema nos mostrará el siguiente aviso:

.. figure:: images/unable-to-assign-moves.png

Dónde podremos visualizar de cada producto las cantidades que no se pueden
reservar (porqué no hay suficiente estoc), junto con sus cantidades. El botón
Forzar reserva nos permitirá asignar igualmente los movimientos, pero sólo nos
aparecerá en caso de que nuestro usuario pertenezca al grupo
|group_stock_force|. También podemos aceptar el aviso con el botón Aceptar.

En caso de que no hayamos forzado las reservas, el albarán quedará en estado
en espera, con los movimientos que se hayan podido reservar en estado
Reservado, y los movimientos pendientes de reservar en estado Borrador.
Podemos cancelar las reservas parciales, utilizando el botón En espera.
Una vez asignados los movimientos de estoc, podemos utilizar el botón
Realizar para finalizar la devolución.

.. |menu_shipment_in_form| tryref:: stock.menu_shipment_in_form/complete_name
.. |menu_shipment_in_return_form| tryref:: stock.menu_shipment_in_return_form/complete_name
.. |in_effective_date| field:: stock.shipment.in/effective_date
.. |in_supplier| field:: stock.shipment.in/supplier
.. |in_warehouse| field:: stock.shipment.in/warehouse
.. |in_incoming_moves| field:: stock.shipment.in/incoming_moves
.. |in_inventory_moves| field:: stock.shipment.in/inventory_moves
.. |in_return_to_location| field:: stock.shipment.in.return/to_location
.. |in_return_moves| field:: stock.shipment.in.return/moves

.. inheritref:: stock/stock:section:envio-de-mercaderia

Envío de mercaderia
===================

Para recibir mercadería debemos crear un albarán de cliente desde la opción
|menu_shipment_out_form|.

Un albarán de cliente es un albarán de salida que nos decrementará las
cantidades de productos en nuestros almacenes.

Los albaranes de cliente están formados por dos tipos de movimiento:

* |out_inventory_moves|: Son aquellos movimientos en que cojemos los
  productos de su ubicación actual (dónde se almacenan) y los preparamos para
  entregarlos al cliente.
* |out_outgoing_moves|: Movimientos que representan la entrega real al
  cliente.

.. |menu_shipment_out_form| tryref:: stock.menu_shipment_out_form/complete_name
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

El primer paso para crear un albarán, es crear sus movimientos de salida.
Una vez creados, podemos utilizar el botón En espera para crear los
movimientos de inventario, automáticamente se nos crearán los movimientos de
inventario necesarios para satisfacer los movimientos de salida.

Al pulsar el botón Reservar el sistema intentará asignar todos los movimientos
de inventario, teniendo en cuenta el stock del almacén.

En caso de que no haya suficiente stock en el almacén para satisfacer todos
los movimientos de inventario, el sistema nos mostrará el siguiente aviso:

.. figure:: images/unable-to-assign-moves.png

Dónde podremos visualizar de cada producto las cantidades que no se pueden
reservar (porqué no hay suficiente estoc), junto con sus cantidades. El botón
Forzar reserva nos permitirá asignar igualmente los movimientos, pero sólo nos
aparecerá en caso de que nuestro usuario pertenezca al grupo
|group_stock_force|. También podemos aceptar el aviso con el botón Aceptar.

.. |group_stock_force| tryref:: stock.group_stock_force_assignment/name

En caso de que no hayamos forzado las reservas, el albarán quedará en estado
en espera, con los movimientos que se hayan podido reservar en estado
Reservado, y los movimientos pendientes de reservar en estado Borrador.
Podemos cancelar las reservas parciales, utilizando el botón En espera.
Una vez asignados los movimientos de estoc, podemos utilizar el botón
Realizar envió para marcar el envío cómo empaquetado.
Los movimientos de inventario estarán completamente realizados, pero los
movimientos de salida estarán reservados, a la espera de ser entregados al
cliente. Una vez entregado al cliente, podemos marcar el albarán cómo
realizado con el botón Realizado.

Recibir devoluciones de mercadería
----------------------------------

A ninguno nos gusta tener clientes descontentos, pero a veces es posible que
nuestros clientes nos devuelvan alguno de los productos que le hemos enviado.
Para gestionarlo debemos crear una devolución de mercaderia desde la opción
|menu_shipment_out_return_form|.

Un albarán de devolución de cliente puede estar en alguno de los siguientes
estados:

* **Borrador**: Estado inicial en que se introducen los movimientos que
  recibimos.
* **Recibido**: Hemos recibido la mercaderia del |out_return_customer| pero
  aún no ha sido almacenada en nuestros almacenes.
* **Realizado**: La mercadería ha sido recibida y almacenada en nuestros
  almacenes.
* **Cancelado**: El albarán ha sido cancelado.

Para crear uno deberemos introducir el |out_return_customer| y el
|out_return_warehouse|. En este momento ya podremos introducir todos los
|out_return_incoming_moves|, para especificar los productos que estamos
recibiendo. Una vez introducidos todos los movimientos, pulsamos sobre el botón
Recibido para realizar todos los |in_incoming_moves|. Una vez realizados,
el sistema nos rellenará los |in_inventory_moves|, pudiéndolos modificar para
especificar en que ubicación los queremos almacenar. Una vez especificada
podemos finalizar la recepción mediante el botón Realizado.

.. |menu_shipment_out_return_form| tryref:: stock.menu_shipment_out_return_form/complete_name
.. |out_return_customer| field:: stock.shipment.out.return/customer
.. |out_return_warehouse| field:: stock.shipment.out.return/warehouse
.. |out_return_incoming_moves| field:: stock.shipment.out.return/incoming_moves
.. |out_return_inventory_moves| field:: stock.shipment.out.return/inventory_moves

.. inheritref:: stock/stock:section:mover-mercaderia-entre-ubicaciones

Mover mercadería entre ubicaciones
==================================

Para mover mercaderia entre ubicaciones podemos crear un albarán interno desde
la opción |menu_shipment_internal_form|.


Un albarán de interno no es un albarán ni de entrada ni de salida. Es un
albarán que contiene productos para un cambio de ubicación dentro de nuestra
empresa, ya sea dentro de un mismo almacén o entre almacenes distintos.
Un albarán de interno puede estar en alguno de los siguientes
estados:

* **Borrador**: Estado inicial en que se introducen los movimientos que
  vamos a devolver.
* **Esperando**: A la espera que la mercadería este disponible en la ubicación
  desde dónde la vamos a enviar.
* **Reservado**: Todos los movimientos han sido reservados para que se puedan
  enviar a la nueva ubicación.
* **Realizado**: La mercadería ha sido entregada.
* **Cancelado**: El albarán ha sido cancelado.

Para crear un albarán interno debemos introducir la ubicación desde dónde
están actualmente los productos en el campo |internal_from_location| y la
ubicación dónde vamos a enviar los productos en el campo
|internal_to_location|. Una vez introducidos podemos introducir los
|internal_moves|. Una vez introducidos, utilizaremos el botón Esperando, para
indicar que estamos a la espera de la mercaderia. Si necesitamos realizar
alguna modificación en el albarán, siempre podemos volver al estado borrador.

En caso de que no haya suficiente stock en la ubicación para satisfacer todos
los movimientos, el sistema nos mostrará el siguiente aviso:

.. figure:: images/unable-to-assign-moves.png

Dónde podremos visualizar de cada producto las cantidades que no se pueden
reservar (porqué no hay suficiente estoc), junto con sus cantidades. El botón
Forzar reserva nos permitirá asignar igualmente los movimientos, pero sólo nos
aparecerá en caso de que nuestro usuario pertenezca al grupo
|group_stock_force|. También podemos aceptar el aviso con el botón Aceptar.

En caso de que no hayamos forzado las reservas, el albarán quedará en estado
en espera, con los movimientos que se hayan podido reservar en estado
Reservado, y los movimientos pendientes de reservar en estado Borrador.
Podemos cancelar las reservas parciales, utilizando el botón En espera.
Una vez asignados los movimientos de estoc, podemos utilizar el botón
Realizar para finalizar la devolución.

.. |menu_shipment_internal_form| tryref:: stock.menu_shipment_internal_form/complete_name
.. |internal_from_location| field:: stock.shipment.internal/from_location
.. |internal_to_location| field:: stock.shipment.internal/to_location
.. |internal_moves| field:: stock.shipment.internal/moves

Cancelar albaranes
==================

En cualquier momento del flujo podremos cancelar los albaranes. Cancelar un
albarán implica cancelar todos los movimientos (tanto los de inventario como
los de entrada/salida) que están en estado borrador o reservado. Los
movimientos que ya están realizados **no se pueden cancelar**.

En caso de que ya hayamos realizado alguno de los movimientos (nos aparecerán
en estado realizado) y cancelemos el albarán, deberemos crear
manualmente un albarán interno para realizar los movimientos en sentido
contrario y volver los productos en sentido contrario.

Una vez cancelado un albarán este puede volver a estado borrador utilizando
el botón Borrador.


.. inheritref:: stock/stock:section:movimientos

Movimientos
===========

Los albaranes de salida, entrada o internos crean movimientos. El listado de todos
los movimientos los podemos consultar a |menu_move_form|.

.. tip:: Podemos utilizar las pestañas para filtrar los movimientos según su
    tipo. Así podemos utilizar los filtros Desde proveedor y Hacia clientes
    para mostrar aquellos movimientos de proveedor o cliente.

.. inheritref:: stock/stock:section:averiguar-terceros-movimiento

Averiguar los terceros a los que hemos recibido o mandado un producto
---------------------------------------------------------------------

Para averiguar los terceros a los que hemos recibido o mandado un producto
debemos realizar un filtro en la pantalla de movimientos, poniendo en el campo
producto el producto que queramos buscar. Además, podemos filtrar por estado
Realizado para excluir aquellos movimientos que todavía no han sido realizados.

Llegados a este punto debemos abrir la vista de formulario de cada uno de los
movimientos para abrir su albarán relacionado y allí podremos ver el tercero
al que ha sido mandado.



.. |menu_move_form| tryref:: stock.menu_move_form/complete_name

Consultar la cantidad de un producto
====================================

Tryton nos provee varias opciones para consultar la cantidad de productos:

.. inheritref:: stock/stock:bullet_list:product-quantity

* **Producto por ubicaciones**: Permite consultar la cantidad disponible de
  un producto para cada ubicación de la empresa.
* **Productos en ubicación**: Permite obtener un listado de todos los
  productos disponibles en una ubicación.

En todas opciones podremos consultar la siguiente información:

* |product_quantity|
* |product_forecast_quantity|
* |product_cost_value|

Además nos permiten obtener la información en una fecha en concreto. Esta fecha
puede ser en el pasado, a día de hoy o en el futuro. La fechas futuras
afectarán a la cantidad prevista y si dejamos la fecha en blanco la cantidad
prevista se mostrará teniendo en cuenta todos los movimientos
introducidos en el sistema (independientemente de su fecha prevista).

El listado de producto por ubicaciones lo podremos abrir desde la opción
|menu_product_form|, seleccionando el producto del que queremos saber las
cantidades, y abriendo la opción **Producto por ubicaciones** que encontraremos
en la Flecha verde de la barra de acciones

Para conocer los **Productos en ubicación** debemos abrir el listado de
ubicaciones que encontraremos en |menu_location_tree| y hacer doble clic sobre
la ubicación que deseamos.

.. inheritref:: stock/stock:paragraph:product-quantity

En todas las consultas podemos utilizar los filtros para realizar búsquedas en
los resultados.

.. |menu_location_tree| tryref:: stock.menu_location_tree/complete_name
.. |menu_product_form| tryref:: product.menu_product/complete_name
.. |product_quantity| field:: product.product/quantity
.. |product_forecast_quantity| field:: product.product/forecast_quantity
.. |product_cost_value| field:: product.product/cost_value

Regularización de existencias
=============================

A veces, es necesario realizar un recuento de las cantidades de producto en el
almacén para validar que la información del sistema se corresponde con la
realidad. Este conteo se conoce como Inventarios, y los podemos generar desde
la opción |menu_inventory_form|.

.. view:: stock.inventory_view_form
   :field: location

Un inventario puede estar en alguno de los siguientes estados:

* **Borrador**: Estado inicial en que se introducen las cantidades.
* **Realizado**: Se ha finalizado el inventario y las existencias han sido
  regularizadas.
* **Cancelado**: El inventario ha sido cancelado.

Para la generación de un inventario deberemos seleccionar la |inv_location|
de dónde queremos realizar el inventario, la ubicación |inv_lost_found| y la
|inv_date| a la que se corresponde.

A partir de aquí podemos introducir los productos que queremos regularizar,
junto con la cantidad actual que hay en el almacén. Una vez finalizado el
recuento podemos utilizar el botón Confirmar, para marcar el albarán cómo
realizado. En este momento Tryton se encargará de realizar los movimientos
necesarios para regularizar las cantidades, cogiendo cómo ubicación de origen
la que hayamos seleccionado en el campo |inv_lost_found|.

Inventario completo
-------------------

Al hacer un inventario podemos de cargar todos los productos para los cuales
el sistema tiene existencias en la |inv_location| utilizando el botón Inventario
completo. Así el sistema, nos creará una linea para cada producto que se
encuentre disponible, rellenando el campo |inv_expected_quantity| con la
el número de existencias del sistema. Una vez llegados a este punto, solo
nos hace falta modificar el campo |inv_quantity| para aquellas lineas en
las que tengamos diferencias reflejando la cantidad real en el almacén.
Cuando hayamos finalizado, utilizaremos el botón Confirmar, para regularizar
las existencias.

.. |menu_inventory_form| tryref:: stock.menu_inventory_form/complete_name
.. |inv_location| field:: stock.inventory/location
.. |inv_lost_found| field:: stock.inventory/lost_found
.. |inv_date| field:: stock.inventory/date
.. |inv_quantity| field:: stock.inventory.line/quantity
.. |inv_expected_quantity| field:: stock.inventory.line/expected_quantity

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
