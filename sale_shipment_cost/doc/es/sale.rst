#:inside:sale/sale:bullet_list:sale_fields#

* |carrier|: Transportista para la entrega
* |shipment_cost_method|: Método de coste de envío

.. |carrier| field:: sale.sale/carrier
.. |shipment_cost_method| field:: sale.sale/shipment_cost_method

#:after:sale/sale:section:lineas_del_pedido_de_venta#

Cálculo del precio de coste del envío
-------------------------------------

En el momento de seleccionar un transportista en el pedido de venta, se generará
una nueva línea en el pedido de venta con el coste y producto del envío.

Cada vez que cambie una línea (ya sea el producto, precio o cantidad) esta línea
se generará de nuevo. En el caso que sea un pedido que ya haya guardado, se eliminará la
línea creando una de nueva.

#:after:sale/sale:section:configuracion#

Coste (transporte) a la factura
-------------------------------

Si en el pedido de venta añadimos un transportista, este añade una línea en el pedido
con el coste del envío. Esta línea no pasará en el albarán ya que es un producto tipo servicio.

Si el método de facturación de un pedido de venta es a partir de albarán, es importante
que a la configuración de las ventas activar la opción "Método coste envío" en el albarán.
Si se selecciona la opción "Método de coste envío" en el pedido se generarán dos facturas,
una factura en el momento de confirmar el pedido y la otra factura en el momento de procesar
el albarán.
