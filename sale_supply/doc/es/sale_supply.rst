======================
Suministra en la venta
======================

Si el producto puede ser comprado, dispondremos de la opción suministra en la venta
en la pestaña *Proveedores* del producto, pero este producto también debe tener 
la marca puede ser vendido. Si la opción está marcada, generará una solicitud de 
compra para cada línea del pedido de venta, independientemente del nivel de 
existencias. Estas solicitudes las encontraremos en el menu Solicitudes de compra. 

Una vez procesada la compra, en la venta que ha generado esta compra se crearán 
los envíos a los clientes, generando los movimientos y albaranes necesarios. 
En el momento que se genera el movimiento de compras, no influye el método de 
facturación en este criterio, ya que los movimientos y albaranes de la compra se 
generarán en cuánto se cree el movimiento de la compra. 

.. inheritref:: sale_suppply/sale_suppply:section:productos_suministro_venta

Productos para el suministro de la venta
========================================

Para crear/modificar productos de suministro directo en venta, seguiremos los
siguientes pasos:

* Abriremos el menú productos.
* Crearemos un producto nuevo o seleccionaremos uno existente.
* Marcaremos las opciones *Puede ser comprado* y *Puede ser vendido*.
* Abriremos la pestaña *Proveedores*.
* Marcaremos la opción suministra en la venta.

Es recomendable relacionar que proveedores ofrecen y entregan el producto en 
cuestión, lo podremos hacer desde la pestaña *Proveedores*, añadiendo línias 
de proveedores, en el listado.

.. |menu_template| tryref:: product.menu_template/complete_name

.. inheritref:: sale_suppply/sale_suppply:section:generacion_solicitudes_compra

Generación solicitudes de compra
================================

Una vez confirmado un pedido de venta, en el momento de procesarlo, se crean
las correspondientes solicitudes de compra, una por cada línea del pedido de
venta. A partir de este momento seguiremos los siguientes pasos:

* Abriremos el menú Solicitudes de compra.
* Seleccionaremos la solicitud de compra deseada.
* Ejecutaremos el asistente **Crear compra**, en este deberemos seleccionar el
  *Proveedor* y el *Plazo de pago*.
* Nos desplazaremos al menú Solicitudes de compra.
* Abriremos y confirmaremos la compra creada mediante el asistente anterior. 
  Esto creará el albarán de salida para el cliente.

.. |menu_purchase_request_form| tryref:: stock_supply.menu_purchase_request_form/complete_name
.. |menu_purchase_form| tryref:: purchase.menu_purchase_form/complete_name

.. |supply_on_sale| field:: product.template/supply_on_sale
