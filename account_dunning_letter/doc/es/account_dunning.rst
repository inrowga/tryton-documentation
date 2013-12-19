#:after:account_dunning/account_dunning:section:reclamaciones#

Informe
=======

Cuando genere una reclamación podemos obtener un informe con el detalle de la
reclamación:

* Apunte pendiente de pago, con la fecha, importe y fecha de vencimiento.
* Pagos pendientes recibidos. Importe y fecha si se han realizado pagos parciales.

Para disponer de un informe es importante que en los procesamientos de las reclamaciones,
a parte del número de dias de retraso, activar la opción |print_on_letter|. Si la opción
|print_on_letter| no está activa, no se mostrarán las reclamaciones en el informe.

En el momento que desea "Procesar reclamación" (asistente) se nos abrirá el
informe con la información de la reclamación.

El informe nos agrupará por cada cliente todos los apuntes que tiene pendiente hacer
el pago y en el caso que dispongamos de pagos pendientes recibidos.

.. |print_on_letter| field:: account.dunning.level/print_on_letter
