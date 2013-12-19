=================
Gestión de Ventas
=================

.. inheritref:: sale/sale:section:venta

Venta
=====

Para crear o listar las ventas accederemos a |menu_sale|.

.. |menu_sale| tryref:: sale.menu_sale_form/complete_name

Una venta está compuesta principalmente por una parte en la que se define el
cliente con sus datos, y otra parte compuesta de líneas en la que se definen
los productos, la cantidad, etc.

.. inheritref:: sale/sale:bullet_list:sale_fields

* |party|: El cliente del pedido de venta.
* |invoice_address|: La dirección de facturación del cliente.
* |shipment_address|: La dirección de envío del cliente.
* |description|: Una descripción opcional del pedido de venta.
* |reference|: La referencia interna de la venta.
* |sale_date|: La fecha en la que se realiza la venta.
* |payment_term|: Define qué plazo de pago debe utilizarse la facturación.
* |warehouse|: Define el almacén desde el que se realiza el envío.
* |currency|: Determina la moneda a utilizar para la venta. Los precios de los
  productos se calcularán de acuerdo a esta selección.
* |untaxed_amount|: La base.
* |tax_amount|: El total de impuestos.
* |total_amount|: El total con impuestos.
* |lines|: Las líneas del pedido de venta.
* |invoice_method|: El método de facturación para este pedido.
* |shipment_method|: El método de envío para este pedido.
* |invoices|: Las facturas relacionadas con este pedido.
* |shipments|: Los abaranes de entrada relacionados con este pedido.
* |moves|: Los movimientos de albaranes relacionados con este pedido.

.. inheritref:: sale/sale:paragraph:el_numero_de_referencia_del_pedido

El número de referencia del pedido de venta (|reference|) se generá en el
momento que este pedido de venta pase de presupuesto a confirmado.

.. |party| field:: sale.sale/party
.. |invoice_address| field:: sale.sale/invoice_address
.. |shipment_address| field:: sale.sale/shipment_address
.. |description| field:: sale.sale/description
.. |reference| field:: sale.sale/reference
.. |sale_date| field:: sale.sale/sale_date
.. |payment_term| field:: sale.sale/payment_term
.. |warehouse| field:: sale.sale/warehouse
.. |currency| field:: sale.sale/currency
.. |lines| field:: sale.sale/lines
.. |untaxed_amount| field:: sale.sale/untaxed_amount
.. |tax_amount| field:: sale.sale/tax_amount
.. |total_amount| field:: sale.sale/total_amount
.. |invoice_method| field:: sale.sale/invoice_method
.. |shipment_method| field:: sale.sale/shipment_method
.. |invoices| field:: sale.sale/invoices
.. |shipments| field:: sale.sale/shipments
.. |moves| field:: sale.sale/moves

.. inheritref:: sale/sale:section:lineas_del_pedido_de_venta

Líneas del pedido de venta
==========================

Un pedido de venta está compuesto por varias líneas en el. Cada línea del
pedido de venta le podremos especificar:

* |sale_line_type|: El tipo de línea. El valor por defecto es *Línea*, lo que
  significa que esta línea de pedido de venta contiene los campos definidos a
  continuación. Los otros valores son *Comentario*, *Subtotal* y *Título* que
  se utilizan para añadir líneas extras que aparecerán en el informe
  permitiendo de esta forma una personalización más sencilla.

En el caso que el tipo de línea sea *línea* le podremos añadir la siguiente
información:

* |sale_line_quantity|: La cantidad. Si la cantidad es un valor negativo, en el
  momento de procesar el pedido este generará albaranes de abono de cliente.
* |sale_line_product|: El producto (opcional).
* |sale_line_description|: La descripción. Se autocompleta si seleccionamos un
  producto.
* |sale_line_unit_price|: El precio. Se autocompleta con el precio del producto.
  Si deseamos cambiar el precio, lo podemos hacer.
* |sale_line_amount|: El total (el precio por la cantidad)

.. |sale_line_type| field:: sale.line/type
.. |sale_line_quantity| field:: sale.line/quantity
.. |sale_line_product| field:: sale.line/product
.. |sale_line_description| field:: sale.line/description
.. |sale_line_unit_price| field:: sale.line/unit_price
.. |sale_line_amount| field:: sale.line/amount

.. inheritref:: sale/sale:paragraph:la_opcion_de_producto

La opción de producto en una línia del pedido de venta es opcional. Si queremos
que estos productos esten en los albaranes, deberemos seleccionar forzosamente
un producto.

.. inheritref:: sale/sale:section:estados

Estados
=======

El listado de continuación muestra los pasos que pasa un pedido de venta:

* Borrador a Presupuesto
* Presupuesto a Confirmado
* Confirmado a En proceso
* Borrador a Cancelado
* Presupuesto a Cancelado
* Presupuesto a Borrador
* Cancelado a Borrador

.. inheritref:: sale/sale:paragraph:estados_cancelado_a_borrador

En el momento de *confirmar* el pedido de venta y pasar *en proceso* se generara
según la configuración de venta:

* Albarán
* Factura

.. warning::  Se generan albaranes sólo si las linias del pedido de venta van
              relacionado con un producto y no sean del tipo servicio.

.. inheritref:: sale/sale:section:devolucion_venta

Devolución de la venta
======================

En el caso de realizar una venta, se ha procesado y finalmente se debe abortar la entrega,
dispone de un asistente para hacer una devolución de la venta.

La acción devolución de la venta simplemente creará una nueva copia de la venta origen
pero con la diferencia que las cantidades de las líneas serán ahora en negativo.

Si las cantidades de las líneas de la venta son en negativo, en el momento de procesar
un albarán en vez de crear un albarán de cliente, se creará un albarán de abono de cliente.

.. inheritref:: sale/sale:section:configuracion

Configuración
=============

A |menu_configuration| nos permite:

.. |menu_configuration| tryref:: sale.menu_configuration/complete_name

* |conf_sequence|
* |conf_invoice_method|
    * Al enviar
    * Al procesar el pedido
    * Manual
* |conf_shipment_method|
    * Al pagar la factura
    * Al procesar el pedido
    * Manual

.. |conf_sequence| field:: sale.configuration/sale_sequence
.. |conf_invoice_method| field:: sale.configuration/sale_invoice_method
.. |conf_shipment_method| field:: sale.configuration/sale_shipment_method
