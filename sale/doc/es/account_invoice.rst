#:after:account_invoice/account_invoice:paragraph:invoice_draft#

Si la factura se genera desde una venta, esta también se creará en estado
*Borrador* con todos los campos rellenados según la información de la venta,
por lo que en este caso, tan solo tendremos que comprobar que los datos son
correctos y *Validar* o *Confirmar* la factura.


#:after:account_invoice/account_invoice:paragraph:excepciones#

Esto provocará que, si la factura se encuentra en estado *Borrador*, al no 
haberse contabilizado todavía, el sistema nos permita cancelarla. Si la factura 
se ha generado desde una venta, en caso de que lo necesitemos, podremos
cancelarla antes de confirmarla. Esta cancelación generará lo que se conoce
como *Excepción de factura* y la gestión pasará al departamento de ventas.
Podemos ver cómo gestionar excepciones en la venta desde
:ref:`sale-exceptions`.