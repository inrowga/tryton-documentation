#before:purchase/purchase:section:configuracion#

=================================
Proceso de cancelación de compras
=================================

Al querer cancelar una compra podemos encontrarnos ante los siguientes casos 
de cancelación, que salvo excepción serán la mayoría:

1. **Cancelar una compra que ha sido introducida y procesada**. Esta compra nos 
   generará uno o más movimientos de producto (en función de la compra) que nos 
   aparecerá en la pestaña *Albaranes* en el campo Movimientos. 
   Para cancelar la compra tan sólo necesitaremos crear un albarán nuevo del 
   tercero, seleccionando el almacén desde el cuál hacemos la recepción. 
   Finalmente, añadiremos la línea de la compra que queremos **Cancelar**, la 
   cancelamos y al volver a la compra (y recargar la ventana) veremos que nos 
   aparece la opción de *gestionar la excepción de envío*. Haremos clic en el 
   botón que nos devolverá un asistente dónde podremos seleccionar los 
   movimientos que queremos recrear. En este caso los **deseleccionaremos** 
   todos, haciendo clic sobre las líneas que por defecto vendrán seleccionadas, 
   y aceptaremos. 
   
   A la conclusión de estos pasos veremos como en la pestaña Albaranes el 
   movimiento y el albarán tienen el estado *Cancelado* y el estado de 
   excepción *Ignorado*. 
   
2. **Cancelar una compra que ha sido recibida y tiene un albarán con el 
   movimiento vinculado**. Si el albarán aún está en estado *Borrador* podremos 
   cancelar tanto la compra como el albarán siguiendo los pasos del punto (1). 
   Ahora bien, si el albarán está *Recibido* lo único que podremos hacer es 
   cancelar el albarán pero la compra ya tendrá el estado *Realizado*, así que 
   deberemos pasar el albarán a *Borrador* para confirmarlo y acabar marcándolo 
   como *Realizado*. Esto nos generará una línea de factura en la compra, 
   llevándonos al siguiente paso: crear una factura de este proveedor, dónde 
   añadiremos la línea de factura de la compra y cancelaremos la factura. Una 
   vez cancelada esta factura nos quedará todo el circuito cerrado ahora bien 
   si queremos hacer la devolución de la mercadería deberemos hacer una copia 
   exacta de la compra inicial con cantidad negativa y procesarla, pero antes 
   de ello es recomendable dirigirnos a la pestaña *Información adicional* y 
   marcar el método de facturación como *Manual*. 
   
   Una vez que hayamos procesado la compra, se generará un movimiento de 
   producto. Este lo añadiremos a un albarán que procesaremos, dando por
   cerrado, así, el circuito de la cancelación de la compra o devolución de
   la mercancía; sin la creación de una nueva línea de factura. 
   
3. **Cancelar una compra que ha sido recibida y no tiene albarán vinculado, 
   pero sí que ha generado una línea de factura**. Repetiremos parte de los 
   pasos enumerados anteriormente, creando una factura de proveedor dónde 
   añadiremos la línea de factura para cancelarla. Realizaremos todas los pasos 
   anteriores hasta llegar de nuevo a la gestión de la excepción de la factura 
   en la compra. Ignorando esta excepción como hemos hecho en casos anteriores.
