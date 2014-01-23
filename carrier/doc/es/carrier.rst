==============
Transportistas
==============

.. inheritref:: carrier/carrier:section:transportistas

Transportistas
==============

Los transportistas van relacionados con un tercero y con un producto.

* Abra el menú |menu_carrier| i cree un nuevo transportista.
* Seleccione el |party| y |carrier_product|.
* Seleccione el |carrier_cost_method|.

El producto relacionado con el transportista debe ser:

* Tipo: servicios
* Para ser vendido
* Precio de venta. Fijar un precio base del envío (no sea 0).

Los |carrier_cost_method| disponibles son:

.. inheritref:: carrier/carrier:bullet_list:carrier_cost_method

* Producto


.. |menu_carrier| tryref:: carrier.menu_carrier/complete_name
.. |party| field:: carrier/party
.. |carrier_product| field:: carrier/carrier_product
.. |carrier_cost_method| field:: carrier/carrier_cost_method
