.. inheritref:: account_asset/account_asset:section:activos

Activos
=======

Configuración
~~~~~~~~~~~~~

Para poder contabilizar activos y su amortización es necesario definir productos
de tipo "Activo" y en la pestaña "Contabilidad" marcar la casilla "Depreciable",
indicando opcionalmente los meses que durará la amortización y estas 4 cuentas contables:

* Cuenta de activo es la cuenta que será utilizada por la factura de proveedor
  para anotar la compra del activo.
* Cuenta de amortización es la cuenta donde se anota la depreciación del activo en
  el haber, y el gasto en el debe de la cuenta de gastos.
* (opcional) Cuenta de ingresos se utilizará para reflejar los posibles ingresos generados
  por la venta del activo (en función de la depreciación ya realizada y el precio de venta).

Por ejemplo:

* Cuenta de activo: 213000 - Maquinaria
* Cuenta de amortización: 281300 - Amortización acumulada de maquinaria
* Cuenta de gastos: 681000 - Amortización del inmovilizado material
* Cuenta de ingresos: 771000 - Beneficios procedentes del inmovilizado material


Creación de activos
~~~~~~~~~~~~~~~~~~~
Para crear un activo debemos ir a la opción |menu_asset|.  En esta pantalla
debemos introducir la información del activo, del que cabe destacar la
siguiente información:

* |product|: Producto a amortizar.
* |account_journal|: Diario contable donde se realizarán los apuntes
  relacionados con el activo.
* |value|: Valor del activo en la fecha inicial de la amortización
* |residual_value|: Valor del activo en la fecha final de la amortización.
* |purchase_date|: Fecha de cuando se compró el activo
* |start_date|: Fecha en que se realizará el primer apunte de amortización.
* |end_date|: Fecha en que se terminará la amortización del activo. Si hemos
  rellenado el número de meses que durará la amortización del producto, este
  campo se calcularà en función de la fecha inicial, aunque podremos
  modificarlo a posteriori.

.. |product| field:: account.asset/product
.. |account_journal| field:: account.asset/account_journal
.. |value| field:: account.asset/value
.. |residual_value| field:: account.asset/residual_value
.. |purchase_date| field:: account.asset/purchase_date
.. |start_date| field:: account.asset/start_date
.. |end_date| field:: account.asset/end_date
.. |supplier_invoice_line| field:: account.asset/supplier_invoice_line
.. |unit| field:: account.asset/unit
.. |quantity| field:: account.asset/quantity

Para previsualizar las líneas de amortización podemos utilizar el botón
`Crear Líneas`. Podemos cambiar el método de amortización y la frequencia de
amortización desde la pestaña Información adicional.  Las líneas se pueden
volver a calcular pulsando el botón `Borrar Lineas` y `Crear Lineas`.

Una vez finalizado la definición del activo, podemos fijar sus líneas
utilizando el botón `Ejecutar`. A partir de este momento se fijarán las
líneas y sólo se podrá modificar el comentario del activo.

Creación desde facturas
~~~~~~~~~~~~~~~~~~~~~~~

Si introducimos una línea de factura de proveedor en el campo
|supplier_invoice_line| el programa se encargará de rellenar todos los datos
del activo a partir de la línea de factura. Los campos que se rellenaràn son
los siguientes:

|purchase_date|: Se utilizará el campo |invoice_date| de la factura.
|value|: Se utilizarà el |invoice_amount| de la línea de factura
|quantity|: Se utilizará la |invoice_quantity| de la línea de factura.
|unit|: Se utilizarà la |invoice_unit| de la línea de factura

.. |invoice_unit| field:: account.invoice.line/unit
.. |invoice_quantity| field:: account.invoice.line/quantity
.. |invoice_amount| field:: account.invoice.line/amount
.. |invoice_date| field:: account.invoice/invoice_date

Processar amortizaciones
~~~~~~~~~~~~~~~~~~~~~~~~

Para generar los apuntes correspondientes a las amortizaciones debemos acceder
a |menu_create_moves|

Se nos abrirá un asistente que nos preguntará hasta que fecha queremos crear
los apuntes. Los apuntes se crearán en estado confirmado. Podemos consultar
los apuntes creados en las líneas de las amortizaciones.

Actualización de activos
~~~~~~~~~~~~~~~~~~~~~~~~

Para cambiar el valor del activo, el valor residual o la fecha final de la
amortización debemos seleccionar el activo por el que queremos cambiar y
utilizar el botón `Actualizar activo`. Se nos abrirá una pestaña donde podremos
seleccionar los nuevos valores para el activo. Una vez modificados los valores
se recalcularán las líneas de de amortización con los nuevos valores.

.. nota:: Este proceso no modificará las líneas ya asentadas, sino que sólo i
            afectará a las líneas pendientes de amortizar.

Finalización de activos
~~~~~~~~~~~~~~~~~~~~~~~

Podemos finalizar la amortización de un activo utilizando el botón `Cerrar` de
la pantalla de activos. Antes de finalizar un activo debemos asegurarnos de
haber generado todos los apuntes de amortización pendiente ya que este proceso
eliminará todas las líneas que no hayan sido asentadas, y generará un apunte
reflejando el cierre del mismo.

Venta de activos
~~~~~~~~~~~~~~~~

La venta de un activo implica la finalización del mismo. Podemos registrar la
venta de un activo directamente desde una factura de cliente. Para ello debemos
seleccionar el producto del activo y nos aparecerá un nuevo campo llamado
|asset|. En este campo debemos seleccionar el activo a vender. Una vez
confirmada la factura de venta, se finalizará el activo.

.. |asset| field:: account.invoice.line/asset
.. |menu_asset| tryref:: account_asset.menu_asset/complete_name
.. |menu_create_moves| tryref:: account_asset.menu_create_moves/complete_name
