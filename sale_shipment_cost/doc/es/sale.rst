#:after:sale/sale:paragraph:campos_venta#

Además, para calcular el precio del coste de envío, deberemos indicar el
transportitsta que realizará la entrega y el método de coste envío en la pestaña
**Información adicional**. En el momento de seleccionar un transportista también se
generará una nueva línea en el pedido de venta con el coste y producto del
envío. Cada vez que cambie una línea (ya sea el producto, precio o cantidad)
esta línea se generará de nuevo. En el caso que sea un pedido que ya se haya
guardado, se eliminará la línea creando una de nueva.

#:after:sale/sale:section:configuracion#

Coste (transporte) a la factura
-------------------------------

Si en el pedido de venta añadimos un transportista, este añade una línea en el pedido
con el coste del envío. Esta línea no pasará en el albarán ya que es un producto tipo servicio.

Si el método de coste envío de un pedido de venta es a partir de albarán, es importante
que en la configuración de las ventas activar la opción "Método coste envío" en el albarán.
Si se selecciona la opción "Método de coste envío" en el pedido se generarán dos facturas,
una factura en el momento de confirmar el pedido y la otra factura en el momento de procesar
el albarán.

