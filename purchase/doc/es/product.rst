#:after:product/product:paragraph:compra-venta#

En caso de que queramos que el producto este disponible para las compras,
debemos marcar el campo |purchasable|. Una vez marcado nos aparecerá una nueva
pestaña **Proveedores**, dónde podremos definir la |purchase_uom|, en caso de
que sea distinta de la |default_uom|. Ademas podemos definir los
|product_suppliers| que nos subministran este producto, junto con el
|supplier_name| y el |supplier_code| propios del Proveedor.

Además, en el campo |lead_time| se puede informar al sistema del tiempo de
entrega del producto por cada proveedor.

.. |purchasable| field:: product.template/purchasable
.. |purchase_uom| field:: product.template/purchase_uom
.. |default_uom| field:: product.template/default_uom
.. |lead_time| field:: purchase.product.supplier/lead_time
.. |product_suppliers| field:: product.template/product_suppliers
.. |supplier_name| field:: purchase.product_supplier/name
.. |supplier_code| field:: purchase.product_supplier/code
