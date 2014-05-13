--------
Facturas
--------

A |menu_account_invoice| gestionaremos toda la facturación de nuestra empresa. En
esta sección podremos gestionar las facturas:

* Factura de cliente
* Factura devolución de cliente
* Factura de proveedor
* Factura devolución de proveedor

Por cada tipo de factura podremos buscar las facturas por:

* Borrador
* Validado
* Confirmado
* Todas

.. inheritref:: account/account_invoice:section:numeracion

Numeración
----------

La numeración de las facturas se establece en la sección de |menu_ir_sequence|.
Por cada año fiscal(|menu_account_fiscalyear|) puede especificar que numeración se
usará.

.. inheritref:: account/account_invoice:section:cuenta

Cuenta
------

Al seleccionar un tercero, a la factura se le anotará la cuenta que dispone del tercero.
En caso contrario, deberá seleccionar una cuenta a la factura.

.. inheritref:: account/account_invoice:section:plazos_de_pago

Plazos de pago
--------------

En las facturas podemos relacionar con un plazo de pago. En el momento que procesamos la factura
se nos crearan líneas de pago según el plazo de pago que le hemos marcado.

En |menu_payment_terms_configuration| podrá añadir los plazos de pago de su empresa.

Cada plazo de pago dispone de varias líneas. Si un pago es a 30 días, este plazo de pago
sólo tendrá una línea. En cambio si el plazo de pago es 15/30 días, debe crear dos
líneas. Veamos algunos ejemplos: 22

* Pago a 30 días. Sólo crearemos una línea:

  * Tipo: Remanete
  * Número de meses: 0
  * Número de semanas: 0
  * Número de días: 30

* Pago a 15/30 días. Crearemos dos líneas:

  * Primera línea:

    * Tipo: Porcentaje sobre total
    * Porcentaje: 50
    * Divisor: 2
    * Número de meses: 0
    * Número de semanas: 0
    * Número de días: 15

  * Segunda línea:

    * Tipo: Remanete
    * Número de meses: 0
    * Número de semanas: 0
    * Número de días: 30

Si el plazo de pago debemos especificar el día, podemos añadir en la opción "Día del mes"
el día que se realizará el plazo de pago.

.. |menu_payment_terms_configuration| tryref:: account_invoice.menu_payment_terms_configuration/complete_name

.. inheritref:: account/account_invoice:section:periodos_fiscales

Períodos fiscales
-----------------

Si es un nuevo año fiscal deberá crear los ejercicios fiscales con sus períodos
(mensuales o trimestrales). Al crear una factura, la fecha de la factura debe concidir
con un período y este esté abierto.

.. inheritref:: account/account_invoice:section:cancelar

Cancelar
--------

Una vez una factura ya esté confirmada, esta no se podrá cancelar. Si desea cancelar una
factura ya confirmada primero deberá generar una factura de abono de este y generar una
de nueva, que se le asignará una nueva numeración.

.. |menu_account_invoice| tryref:: account_invoice.menu_invoices/complete_name
.. |menu_account_fiscalyear| tryref:: account.menu_fiscalyear_form/complete_name
.. |menu_ir_sequence| tryref:: ir.menu_sequences/complete_name

.. inheritref:: account/account_invoice:section:abono

Abono
-----

En las facturas de cliente disponemos del asistente para generar el abono: "Abono" y marcar la opción
"Devolución". La factura cliente se confirmará y se conciliará (para hacer un abono completo).
Si no marcamos la opción "Devolución" nos hará un abono borrador, donde podremos modificar o eliminar
líneas antes de confirmarlo (para hacer un abono parcial).

En el caso de disponer el abono hecho pendiente de conciliar, y lo que deseamos es simplemente como
conciliar mutuamente una factura y su factura de abono, es lo mismo que conciliar facturas con pagos.
Iremos al atajo/realación "Cuentas a cobrar" del tercero y veremos sus apuntes pendiente de conciliación,
de facturas, de abonos, de cobros o devolución de cobros. Marcamos los que la suma debe y haber coinciden
y ejecutamos la acción "Conciliar apuntes".
