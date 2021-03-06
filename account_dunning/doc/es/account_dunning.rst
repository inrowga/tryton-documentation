
=================
Límite de crédito
=================

Podemos controlar el crédito que le estamos facilitando a uno de 
nuestros clientes a través del *Importe de crédito* que aparece en la pestaña 
Contabilidad de la ficha del tercero. Dónde además veremos el 
*límite de crédito por defecto* indicado, que podremos modificar si queremos en 
cada tercero. Pero que habremos configurado previamente.

Configuraremos el *límite de crédito por defecto* en el menu Contable de la 
configuración de Contabilidad. Podremos definirlo de forma génerica para todos 
los terceros. Ahora bien, en función de los permisos que tengamos podremos 
editar o no el límite de crédito del tercero. 

.. view:: account.configuration_view_form

   Captura de la pantalla de configuración contable

Por otro lado también podremos seleccionar la opción de control del límite de 
crédito en el menu de las reclamaciones, al crear un nivel de reclamación, que 
nos aparecerá junto con el *números de días de atraso* y la *secuencia*, al crear un 
*nivel de reclamación* en el procedimiento de la reclamación. Esta opción al 
marcarla, nos permitirá tener un control sobre próximas operaciones o gestiones 
con el tercero, al cuál se le emitirá una reclamación si excede este límite.

.. view:: account_dunning.dunning_level_view_form

   Captura de la pantalla del menu reclamaciones

Informe
=======

Cuando genere una reclamación podemos obtener un informe con el detalle de la
reclamación:

* Apunte pendiente de pago, con la fecha, importe y fecha de vencimiento.
* Pagos pendientes recibidos. Importe y fecha si se han realizado pagos parciales.

Para disponer de un informe es importante que en los procesamientos de las reclamaciones,
a parte del número de días de retraso, activar la opción imprimir en carta. Si la opción
imprimir en carta  no está activa, no se mostrarán las reclamaciones en el informe.

En el momento que desea "Procesar reclamación" (asistente) se nos abrirá el
informe con la información de la reclamación.

El informe nos agrupará por cada cliente todos los apuntes que tiene pendiente hacer
el pago y en el caso que dispongamos de pagos pendientes recibidos.
  

Reclamaciones
=============

Con las reclamaciones podrá controlar los pagos de los clientes y notificar a 
los clientes de los pagos pendientes.

Para consultar las reclamaciones que se van creando con un tercero puede consultar
des del tercero mediante la acción Reclamaciones.

También puede consultar las reclamaciones al formulario de reclamacion.

Al menu crear reclamacion dispone de un asistente que podrá crear las reclamaciones
especificando una fecha. Según la fecha del asistente, se nos crearán las reclamaciones
según la fecha del apunte y los números de retraso que especificamos en la configuración
del procedimiento de la reclamación.  

Las reclamaciones que se crean irán relacionadas con un apunte contable que es el apunte
que está pendiente de pago.

Para notificar las reclamaciones seleccione las reclamaciones que desea enviar y accione
el asistente "Procesar reclamación". La reclamación finalmente pasará al estado realizada.

Configuración
=============

En la configuración de la contabilidad dispone del valor por defecto de la reclamación que 
se va a usar en los movimientos contables. Si lo desea, también por cada tercero podrá especificar
el tipo de reclamación si es diferente de la configuración global.
