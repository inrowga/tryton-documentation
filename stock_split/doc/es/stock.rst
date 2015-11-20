#:after:stock/stock:section:movimientos#

.. inheritref:: stock/stock:section:split_moves

-----------------
Dividir albaranes
-----------------

A las líneas de albarán dispone de un asistente que permite dividir las lineas del
albarán. Debe especificar las cantidad a dividir y ese albarán se dividirá en dos.

Si se rellena el campo |count|, sólo se dividirá ese número de veces. Puede
crearse una línea con la cantidad restante.

.. |count| field:: stock.move.split.start/count

