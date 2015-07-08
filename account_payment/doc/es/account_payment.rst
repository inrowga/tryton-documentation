Pagos y cobros
**************

.. TODO 
   Desenvolupar algunes coses massa esquemàtiques i eliminar possibles errors.

Configuración
-------------

.. inheritref:: account_payment/account_payment:paragraph:configuracion

**Tryton** gestiona los cobros y los pagos a través de los |payment_journal|,
por lo que antes de realizar cualquier gestión, deberemos configurar al menos
uno. Para ello accederemos a |menu_payment_journal| y en la pestaña que se nos
abrirá clicaremos en *Nuevo*. En el formulario que se nos abrirá tendremos que
indicar el |name|, la |company|, la |currency| y el |process_method|.

Dentro del listado de Métodos de proceso entre otros podemos encontrar los 
siguientes: 

  MANUAL -> Pagaré
  SEPA CORE DIRECT DEBIT -> Giro
  SEPA CREDIT TRANSFER -> Transferencia

Los anteriores son los más comunes pero, como vemos, cada uno de estos métodos 
va vinculado a un tipo de pago del emisor. Al asignar un método y un tipo de 
pago a un diario de pago los pagos creados en grupos de pago solo podrán ser 
del mismo tipo que los del diario.

Una vez ya tengamos configurado al menos un diario, podremos acceder al listado
de los efectos a pagar o cobrar y también podremos informar pagos o cobros en
el sistema.

Listar efectos pendientes de cobro o pago
------------------------------------------

.. inheritref:: account_payment/account_payment:paragraph:efectos

Cuando se confirma un asiento, ya sea porque lo introducimos manualmente o
porque se genera a partir de una factura, se crea a su vez en el sistema un
efecto. Si accedemos a |menu_efects| podremos ver listados todos los efectos
que tenemos pendientes de pagar y cobrar separados por pestañas. 

.. inheritref:: account_payment/account_payment:section:pagos

Informar un pago o un cobro
---------------------------

Aunque hay muchas formas de hacerlo, desde el menú |menu_payment| también
podremos informar al sistema del pago o cobro de un efecto. Si introducimos el
|party| y el |kind| de pago, en el campo |line| nos aparecerán todos los efectos
pendientes de pagar del cliente. Una vez seleccionado el efecto el resto de
campos se rellenarán con la información del efecto. Si estamos introduciendo un
anticipo, por ejemplo, y no hay un efecto como contrapartida, tendremos que
rellenar manualmente en resto de campos.

Cuando tengamos toda la información introducida deberemos clicar en *Aprobar*,
con esto indicamos al sistema que el pago o el cobro del efecto ha sido
aceptado por el responsable de la empresa. Para procesar un pago (lo que
representa que hemos mandado la orden de pago o cobro al banco) tendremos que
acceder a la pestaña *Aprobado*, seleccionar todos los pagos que se realizarán
en la remesa (o uno solo si la orden solo se realiza por un pago) y tras clicar
en el icono *Ejecutar acción* seleccionaremos la opción *Procesar pagos*. Una
vez nos contesten del banco, podremos indicar en la pestaña *En proceso* si los
pagos se han realizado *Con éxito*, o si nos lo han rechazado y por tanto ha 
*Fallado*.

.. note:: Posteriormente podremos acceder a |menu_payment_groups| para acceder
          a la información de la remesa y los pagos de esta. 

Si el pago se ha realizado con éxito, el efecto dejara de aparecer en el
listado de *Efectos a pagar/cobrar* y si le indicamos que el pago ha fallado
seguirá apareciendo en el listado.

.. |payment_journal| tryref:: account_payment.menu_payment_journal_form/name
.. |menu_payment_journal| tryref:: account_payment.menu_payment_journal_form/complete_name
.. |name| field:: account.payment.journal/name
.. |company| field:: account.payment.journal/company
.. |currency| field:: account.payment.journal/currency
.. |process_method| field:: account.payment.journal/process_method
.. |menu_efects| tryref:: account_payment.menu_move_line_form/complete_name
.. |menu_payment| tryref:: account_payment.menu_payment_form/complete_name
.. |party| field:: account.payment/party
.. |kind| field:: account.payment/kind
.. |line| field:: account.payment/line
.. |menu_payment_groups| tryref:: account_payment.menu_payment_group_form/complete_name