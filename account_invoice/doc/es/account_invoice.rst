.. inheritref:: account_invoice/account_invoice:title:invoicing

-----------
Facturación
-----------

.. _gestion-facturas:

Desde |menu_account_invoice| podremos gestionar toda la facturación de nuestra
empresa, tanto las facturas que emitimos a nuestros clientes, como las que
nos emiten nuestros proveedores, ya que el sistema distingue entre distintos
tipos de facturas dependiendo de si se generan por una venta, una compra o por
una devolución de estas. Desde el menú de facturación podremos acceder a
cualquiera de los tipos de factura:

* |factura_cliente|
* |factura_proveedor|

Para cada una de las distintas tipologías, el funcionamiento que
encontraremos será el mismo: Podremos encontrar la factura en distintos estados
dependiente de en qué punto se encuentre el proceso de facturación. Los estados
en lo que podremos encontrar una factura son:

.. inheritref:: account_invoice/account_invoice:paragraph:invoice_draft

* **Borrador**: Será el estado en el que se genere la factura y el único en
  el que se permita su edición, por lo que mientras factura se encuentre en
  este estado podremos modificar cualquier campo que deseemos (excepto el
  campo |number| que se rellenará automáticamente cuando confirmemos la
  factura). Cuando ya tengamos todos los campos rellenados
  podremos modificar el estado de la factura clicando en el botón *Validar* o
  en el botón *Confirmar*.

* **Validada**: Cuando validamos una factura, la edición de los campos se
  bloquea y el sistema ya no nos permite modificarla. Aun así, podemos cambiar
  el estado de nuevo a *Borrador* en cualquier momento para hacer alguna
  modificación. El estado validado no genera ningún asiento contable, es lo que
  también se conoce como factura pro forma. Hay que tener en cuenta que no es
  un paso previo al estado *Confirmado*, solo un estado en el que puede estar
  la factura antes de ser confirmada, si no trabajamos con Facturas pro forma
  podemos confirmar la factura directamente desde el estado *Borrador*.

* **Confirmada**: Una vez confirmemos la factura, el sistema automáticamente le
  dará un número y la contabilizará generando un asiento contable en nuestro
  registro. Este es un paso definitivo y una vez esté la factura confirmada
  no se podrá volver a cambiar de estado y, por lo tanto, tampoco se podrá
  modificar.

* **Pagada**: La factura pasará a estado *Pagada* cuando le indiquemos al
  sistema que se ha realizado el pago. Para ello tendremos dos formas: si el
  pago de esta factura se hace en efectivo, clicaremos en el botón *Pagar*,
  y se generará un asiento conciliando los apuntes de pago con los generados
  por la factura; en caso de que el pago se realice por cualquier otro método,
  cuando conciliemos los apuntes generados por la factura, el sistema
  reconocerá que esta ha sido pagada y su estado cambiará a *Pagada*.

Los campos que podemos encontrar en una factura son:

.. inheritref:: account_invoice/account_invoice:bullet_list:fields

* |party|: Al seleccionarlo se nos rellenarán varios campos como |account| o
  |currency| con la información que tengamos registrada del |party|.
* |number|: Cuando confirmemos la factura se rellenará automáticamente este
  campo siguiendo la secuencia que le hayamos indicado previamente
  (:ref:`admin-secuencias`).
* |reference|: En este campo podremos indicar cualquier referencia que nos pueda
  ayudar en nuestra gestión. En las factura de proveedor solemos utilizar este
  campo para indicar la numeración que le da el proveedor a la factura, y que
  será diferente al campo |number|.
* |invoice_date|: Se utilizará como referencia para el registro contable,
  contabilizándose en el mes y año indicado el asiento contable que genere la
  factura. En las facturas de cliente, en caso de que no rellenemos nosotros
  el campo, el sistema lo hará de forma automática con la fecha actual en el
  momento de confirmar la factura. En cambio, en las facturas de proveedor no
  nos permitirá avanzar mientras no le indiquemos la fecha en la que el
  proveedor nos emitió la factura.
* |payment_term|: Aquí deberemos seleccionar el plazo de pago que tendrá la
  factura, entre los tipo de plazos que hayamos configurado previamente
  (:ref:`Configurar plazos de pago<configurar-plazos>`).
* |lines|: En este campo es donde indicaremos las líneas de las que se compone
  la factura. Para ello clicaremos en el botón *Nuevo* del propio campo y se
  nos abrirá una ventana donde podremos rellenar los distintos campos que
  componen la línea:

   * |line_type|: Dependiendo de la tipología que elijamos, la
     línea funcionará como un título, añadirá un comentario, reflejará un
     subtotal o actuará de línea de factura propiamente dicha. De estas cuatro
     tipologías, las tres primeras se componen únicamente de los campos
     |line_description| y |line_sequence|. Si seleccionamos como |line_type|
     línea, también tendremos que rellenar los siguientes campos:
   * |line_product|: Aquí seleccionaremos el producto del cual será objeto la
     línea de la factura.
   * |line_description|: En este campo reflejaremos aquello que aparecerá
     como descripción de la línea en la factura. Si indicamos previamente el
     |line_product|, este campo se rellenará automáticamente con el nombre
     del producto, aunque podremos modificarlo.
   * |line_account|: Deberemos indicar la cuenta contable donde se
     contabilizará la línea.
   * |line_quantity| y |line_unit|: Indicaremos la cantidad y la unidad de
     medida del producto que estamos introduciendo.
   * |line_unit_price|: Cuando indiquemos aquí el precio por unidad al que
     vendemos/compramos el producto, se nos rellenará de forma automática el
     campo |line_amount| con el total de la línea.
   * |line_taxes|: Si tenemos configurados los productos con el impuesto que
     les corresponde, este campo se nos rellenará automáticamente con la
     información indicada en el producto.

* |taxes|: Refleja toda la información que le hemos indicado en los
  |line_taxes| con la base imponible total de todos los productos por impuesto.

.. inheritref:: account_invoice/account_invoice:paragraph:prevent_duplicates

Si cambiamos a la pestaña **Información adicional** podremos acceder a la
información contable de la factura, y, una vez confirmada, podremos acceder
por medio del icono en forma de carpeta del campo |move| a la información
detallada de los apuntes contables generados por la factura.

En la pestaña **Pago**, también una vez confirmada la factura, se nos
rellenarán automáticamente los campos |amount_to_pay_today| y |amount_to_pay|,
teniendo en cuenta el |total_amount| de la factura y el |payment_term| que le
hayamos indicado.

.. inheritref:: account_invoice/account_invoice:section:cancelar

Cancelar una factura
--------------------

.. inheritref:: account_invoice/account_invoice:paragraph:excepciones

Si una factura ya está confirmada, **Tryton** no nos permitirá cancelarla o
anularla. Para poder hacerlo deberemos generar una factura de abono que anule
contablemente la que queremos cancelar, de la misma forma que si el cliente nos
hiciera una devolución de material (solo que esta no quedará reflejada en los
movimientos de stock). Si la cancelación la hacemos porque la factura tiene un
error y no la podemos modificar, tendremos que generar otra nueva una vez
anulemos la original. En este caso tendremos que tener en cuenta que a esta
nueva factura se le asignará un nuevo número de factura distinto al de la
original.

.. inheritref:: account_invoice/account_invoice:section:abono

Abonar una factura
------------------

En las facturas de cliente disponemos de un asistente que nos facilita la tarea
de abonar una factura. Para acceder a él clicaremos en el botón *Acciones* y,
seleccionando *Abono*, se nos abrirá una ventana donde deberemos indicar si el
abono de la factura se hará con devolución o sin. Si queremos realizar un abono
total de la factura seleccionamos *Con devolución*, ya que así la factura de
abono se confirmará y se conciliará automáticamente con la factura abonada. En
cambio si tan solo queremos hacer un abono parcial de una factura deberemos
deseleccionar la opción *Con devolución*, de esta manera se nos generará una
factura de abono en estado borrador, dónde podremos modificar o eliminar las
líneas que queramos antes de confirmar la factura.

En las facturas de proveedor el procedimiento es más corto y rápido. En el
momento que queremos abonar la factura, abrimos el desplegable *Accions* y
seleccionamos la acción *Cancelar*. Este movimiento provocará que
automáticamente se abone la factura. Cancelándose cualquier movimiento de
inventario y creando, por defecto, los asientos contables de abono,
conciliándolos con la factura de proveedor que queríamos abonar.


.. |menu_account_invoice| tryref:: account_invoice.menu_invoices/complete_name
.. |factura_cliente| tryref:: account_invoice.menu_invoice_out_form/name
.. |factura_proveedor| tryref:: account_invoice.menu_invoice_in_form/name
.. |party| field:: account.invoice/party
.. |reference| field:: account.invoice/reference
.. |invoice_date| field:: account.invoice/invoice_date
.. |account| field:: account.invoice/account
.. |currency| field:: account.invoice/currency
.. |number| field:: account.invoice/number
.. |payment_term| field:: account.invoice/payment_term
.. |lines| field:: account.invoice/lines
.. |taxes| field:: account.invoice/taxes
.. |move| field:: account.invoice/move
.. |amount_to_pay_today| field:: account.invoice/amount_to_pay_today
.. |amount_to_pay| field:: account.invoice/amount_to_pay
.. |total_amount| field:: account.invoice/total_amount
.. |line_type| field:: account.invoice.line/type
.. |line_description| field:: account.invoice.line/description
.. |line_sequence| field:: account.invoice.line/sequence
.. |line_product| field:: account.invoice.line/product
.. |line_account| field:: account.invoice.line/account
.. |line_quantity| field:: account.invoice.line/quantity
.. |line_unit| field:: account.invoice.line/unit
.. |line_unit_price| field:: account.invoice.line/unit_price
.. |line_amount| field:: account.invoice.line/amount
.. |line_taxes| field:: account.invoice.line/taxes


