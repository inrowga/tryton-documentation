Suministra en la venta
======================

Si el producto puede ser comprado, dispondremos de la opción |supply_on_sale|
en la pestaña *Proveedores* del producto. Si la opción está marcada, generará
un pedido de compra para cada línea del pedido de venta independientemente del
nivel de existencias. Cuando se procesa la compra, se crean los envíos de los
clientes. Una vez se reciben los productos comprados, se asignan a los envíos
de los clientes.

.. inheritref:: sale_suppply/sale_suppply:section:productos_suministro_venta

Productos para el suministro de la venta
========================================

Para crear/modificar productos de suministro directo en venta, siga los
siguientes pasos:

* Abra el menú |menu_template|.
* Cree un producto nuevo o seleccione uno existente.
* Marque las opciones *Puede ser comprado* y *Puede ser vendido*.
* Abra la pestaña *Proveedores*.
* Marque la opción |supply_on_sale|.

Recomenable en el producto relacionar que proveedores ofrecen este producto y entrega.

.. |menu_template| tryref:: product.menu_template/complete_name

.. inheritref:: sale_suppply/sale_suppply:section:generacion_solicitudes_compra

Generación solicitudes de compra
================================

Una vez confirmado un pedido de venta, en el momento de procesarlo, se crea
las correspondientes solicitudes de compra, una por cada línea del pedido de
venta. A partir de este momento siga los siguientes pasos:

* Abra el menú |menu_purchase_request_form|.
* Abra o seleccione la solicitud de compra deseada.
* Ejecute el asistente **Crear compra**. Para ello deberá seleccionar el
  **Proveedor** y el **Plazo de pago**.
* Abra el menú |menu_purchase_form|.
* Abra y confirme la compra creada mediante el asistente anterior. Esto creará
  el albarán de salida para el cliente.

.. |menu_purchase_request_form| tryref:: stock_supply.menu_purchase_request_form/complete_name
.. |menu_purchase_form| tryref:: purchase.menu_purchase_form/complete_name

.. |supply_on_sale| field:: product.template/supply_on_sale
