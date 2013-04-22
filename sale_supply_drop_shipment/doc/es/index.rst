=============
Envío directo
=============

Añadre la opción |drop_shipment| en la pesataña de proveedor del producto si está
marcada la opción |purchasable| del producto. Cuando se activa, la solicitud de
compra y la compra vinculada tienen la dirección del cliente como dirección de
entrega; cuando se confirma la venta, se crea un envío directo y enlaza la
compra y la venta.

.. |drop_shipment| field:: purchase.product_supplier/drop_shipment
.. |purchasable| field:: product.template/purchasable

.. warning:: En la información del proveedores del producto, deberán anotar
               también el tiempo de entrega aunque no sea un campo requerido.

El envío directo se utiliza cuando los productos se envían directamente desde
el proveedor al cliente sin pasar por el almacén. Está compuesto principalmente
de un proveedor, un cliente y una lista de movimientos de stock.

Un envío directo puede estar en uno de los siguientes estados:

* Borrador: Todos los movimientos de stock están en estado borrador.
* En espera: Todos los movimientos de stock están en estado borrador, pero el
  envío está en estado de sólo lectura.
* Realizado: Todos los movimientos de stock están en estado realizado.
* Cancelado: Todos los movimientos de stock están en estado cancelado.

Generación de envíos directos
=============================

Una vez creado el pedido de venta, una vez lo procese, este generará solicitudes
de compra asignado ya con el mejor proveedor (según los valores del tiempo de
entrega del proveedor).

Cuando esta solicitud de compra pasa ya a ser una compra (con la acción *Crear compra*),
este en vez de crea un albarán de proveedor, se crea un albarán de envío directo
de proveedor a cliente (en inglés, drop shipment).

Para acceder a los albaranes de envío directo, accederemos al menú |menu_shipment_drop|.

.. |menu_shipment_drop| tryref:: sale_supply_drop_shipment.menu_shipment_drop_form/complete_name

Dependencias
------------

* Empresa_
* `Venta por suministro`_

.. _Empresa: ../company/index.html
.. _Venta por suministro: ../sale_supply/index.html
