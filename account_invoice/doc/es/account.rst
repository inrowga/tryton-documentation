#:before:account/account:section:asientos_y_movimientos#

.. inheritref:: account/account_invoice:section:facturas

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
