==================
Gestión de Compras
==================

.. inheritref:: purchase/purchase:section:compra

Compra
======

Para crear o listar las ventas accederemos a |menu_purchase|.

.. |menu_purchase| tryref:: purchase.menu_purchase_form/complete_name

Una venta de compra está compuesta principalmente por una parte en la que se define
el proveedor con sus datos, y otra parte compuesta de líneas en la que se definen
los productos, la cantidad, etc.

* |party|: El proveedor.
* |invoice_address|: La dirección de facturación del proveedor.
* |reference|: La referencia nuestra del pedido de compra.
* |supplier_reference|: La referencia del proveedor del pedido de compra.
* |description|
* |purchase_date|: La fecha en la que se realiza el pedido.
* |payment_term|: Define qué plazo de pago debe utilizarse la facturación.
* |untaxed_amount|: La base.
* |tax_amount|: El total de impuestos.
* |total_amount|: El total con impuestos.
* |lines|: Las líneas del pedido de compra.
* |invoice_method|: Método de facturación.
    * Al enviar
    * Al procesar el pedido
    * Manual
* |invoices|: Las facturas relacionadas con este pedido.
* |shipments|: Los abaranes de entrada relacionados con este pedido.
* |shipment_returns|: Los albaranes de devolución relacionados con este pedido.
* |moves|: Los movimientos de albaranes relacionados con este pedido.

.. inheritref:: purchase/purchase:paragraph:el_numero_de_referencia_del_pedido

El número de referencia del pedido de venta (|reference|) se generá un código
en el momento que este pedido de compre pase de presupuesto a confirmado.

.. |party| field:: purchase.purchase/party
.. |invoice_address| field:: purchase.purchase/invoice_address
.. |reference| field:: purchase.purchase/reference
.. |supplier_reference| field:: purchase.purchase/supplier_reference
.. |description| field:: purchase.purchase/description
.. |purchase_date| field:: purchase.purchase/purchase_date
.. |payment_term| field:: purchase.purchase/payment_term
.. |untaxed_amount| field:: purchase.purchase/untaxed_amount
.. |tax_amount| field:: purchase.purchase/tax_amount
.. |total_amount| field:: purchase.purchase/total_amount
.. |lines| field:: purchase.purchase/lines
.. |invoice_method| field:: purchase.purchase/invoice_method
.. |invoices| field:: purchase.purchase/invoices
.. |shipments| field:: purchase.purchase/shipments
.. |shipment_returns| field:: purchase.purchase/shipment_returns
.. |moves| field:: purchase.purchase/moves

.. inheritref:: purchase/purchase:section:lineas_del_pedido_de_compra

Líneas del pedido de compra
===========================

Un pedido de compra está compuesto por varias líneas en el. Cada línea del pedido
de compra le podremos especificar 

* |line_type|: El tipo de línea. El valor por defecto es *Línea*, lo que significa
  que esta línea de pedido de venta contiene los campos definidos a
  continuación. Los otros valores son *Comentario*, *Subtotal* y *Título* que se
  utilizan para añadir líneas extras que aparecerán en el informe permitiendo de
  esta forma una personalización más sencilla.

En el caso que el tipo de línea sea *línea* le podremos añadir la siguiente
información:

* |line_quantity|: La cantidad.
* |line_product|: El producto (opcional).
* |line_description|: La descripción. Se autocompleta si seleccionamos un
  producto.
* |line_unit_price|: El precio. Se autocompleta con el precio del producto.
  Si deseamos cambiar el precio, lo podemos hacer.
* |line_amount|: El total (el precio por la cantidad)

.. |line_type| field:: purchase.line/type
.. |line_quantity| field:: purchase.line/quantity
.. |line_product| field:: purchase.line/product
.. |line_description| field:: purchase.line/description
.. |line_unit_price| field:: purchase.line/unit_price
.. |line_amount| field:: purchase.line/amount

.. inheritref:: purchase/purchase:paragraph:la_opcion_de_producto

La opción de producto en una línia del pedido de compra es opcional. Si queremos
que estos productos esten en los albaranes, deberemos seleccionar forzosamente
un producto.

.. inheritref:: purchase/purchase:section:estados

Estados
=======

Los estados de un pedido de compra són:

* Borrador a Presupuesto
* Presupuesto a Confirmado
* Borrador a Cancelado
* Presupuesto a Cancelado
* Presupuesto a Borrador
* Cancelado a Borrador

.. inheritref:: purchase/purchase:paragraph:cuando_un_pedido_de_compra_activamos_el_estado

Cuando un pedido de compra activamos el estado de *confirmar* se generara según
la configuración del pedido:

* El albarán de entrada
* La factura de proveedor

.. warning::  Se generan albaranes sólo si las linias del pedido de compra van
              relacionado con un producto y no sean del tipo servicio.

.. inheritref:: purchase/purchase:section:configuracion

Configuración
=============

A |menu_configuration| nos permite:

.. |menu_configuration| tryref:: purchase.menu_configuration/complete_name

* |conf_purchase_sequence|
* |conf_purchase_invoice_method|
    * Al enviar
    * Al procesar el pedido
    * Manual
    
.. |conf_purchase_sequence| field:: purchase.configuration/purchase_sequence
.. |conf_purchase_invoice_method| field:: purchase.configuration/purchase_invoice_method
