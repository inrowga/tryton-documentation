#:after:stock/stock:paragraph:albaranes_espera#

En este estado se generarán también los albaranes derivados de una venta
(siempre que se venda algún producto de tipo *Bienes*). Estos albaranes
contendrán en los movimientos de salida todos los movimientos generados por la
venta y en los movimientos de inventario los movimientos necesarios para
satisfacer los movimientos de salida.



#:after:stock/stock:paragraph:exception#

En cambio, si cancelamos un albarán que procede de una venta, se generará una
*Excepción en el envío* y la gestión pasará al departamento de ventas, por lo
que el sistema no nos dejará volverlo a pasar a *Borrador*. Podemos ver cómo
gestionar las excepciones en el envío desde :ref:`sale-exceptions`.


#:before:stock/stock:section:cancelar#

Entregas parciales
~~~~~~~~~~~~~~~~~~

Para que las entregas parciales funcionen correctamente los albaranes de
cliente deben haber sido creados a través de una venta, ya que a través de la
misma el sistema podrá saber cuales son las cantidades de cada producto que
todavía están pendientes de enviar.

En caso de que no haya suficiente stock de algún producto, podemos hacer una
entrega parcial. Para ello, debemos eliminar las líneas en estado borrador de
las líneas de inventario. Una vez eliminadas, podemos reservar el albarán ya
que todos los movimientos estarán reservados. Cuando se realice el envío se
actualizarán las cantidades de los movimientos de salida, reflejando las
cantidades realmente asignadas.

Una vez realizado el albarán, se generará un nuevo albarán en estado En espera
con los movimientos pendientes de realizar. Podremos ver todos los movimientos
y albaranes generados desde la pestaña Albaranes de la venta relacionada, tal
como se muestra a continuación:

.. figure:: images/shipments-from-sale.png

Desde allí podemos ver los movimientos pendientes, aquellos con estado Borrador,
junto con los albaranes pendientes, aquellos con estado En espera.
