.. inheritref:: account_dunning/account_dunning:section:reclamaciones

Con las reclamaciones podrá controlar los pagos de los clientes y notificar a 
los clientes de los pagos pendientes.

Para consultar las reclamaciones que se van creando con un tercero puede consultar
des del tercero mediante la acción Reclamaciones.

También puede consultar las reclamaciones a |menu_dunning_procedure_form|.

A |menu_dunning_create| dispone de un asistente que podrá crear las reclamaciones
especificando una fecha. Según la fecha del asistente, se nos crearán las reclamaciones
según la fecha del apunte y los números de retraso que especificamos en la configuración
del procedimiento de la reclamación.  

Las reclamaciones que se crean irán relacionadas con un apunte contable que es el apunte
que está pendiente de pago.

Para notificar las reclamaciones seleccione las reclamaciones que desea enviar y accione
el asistente "Procesar reclamación". La reclamación finalmente pasará al estado realizada.

.. |menu_dunning_procedure_form| tryref:: account_dunning.menu_dunning_procedure_form/complete_name
.. |menu_dunning_create| tryref:: account_dunning.menu_dunning_create/complete_name

.. inheritref:: account_dunning/account_dunning:section:configuracion

Configuración
=============

En la configuración de la contabilidad dispone del valor por defecto de la reclamación que 
se va a usar en los movimientos contables. Si lo desea, también por cada tercero podrá especificar
el tipo de reclamación si es diferente de la configuración global.
