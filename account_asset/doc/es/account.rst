#:before:account/account:section:activos#

=================
Amortizar activos
=================
Mediante la depreciación de activos podemos repartir el coste de las
inversiones entre los diferentes ejercicios fiscales en los que se produce su uso
o disfrute en la actividad empresarial. De esta forma se refleja más fielmente el
estado contable de nuestra empresa.

Antes de crear un plan de amortización, debemos tener configurado el producto sobre
el que realizaremos la amortización. En el apartado
:ref:`product-para-amortizacion-de-activos` se detalla cómo debemos crear
producto para poder gestionar su amortización. Así, como luego veremos, 
cuando creemos el plan de amortización, sólo podremos seleccionar aquellos
productos de tipo activo que hayan sido marcados como |depreciable|.

Una vez tengamos el producto ya creado, deberemos ir al menú |menu_asset|.
Una vez dentro tendremos una vista de todos los planes de amortización
según su estado (*Borrador*: Planes que todavía no están confirmados; *En ejecución*:
Activos cuyas amortizaciones se están llevando a cabo; *Cerrado*: Activos ya
finalizados; y *Todo*: Todos los planes introducidos). Para introducir un nuevo
plan de amortización deberemos clicar en el icono  *Nuevo* y nos llevara a la vista
de edición, donde deberemos rellenar los siguiente campos:

* |product|: Indicaremos el producto a amortizar. Podemos buscar entre los productos
  que ya tenemos informados como *activos* o generar uno nuevo siguiendo los pasos
  indicados anteriormente.
* |account_journal|: Elegiremos el diario contable en el que queramos que se queden
  reflejados los apuntes relacionados con el activo.
* |supplier_invoice_line|: En caso de que se haya generado una factura con la
  compra del activo introduciremos aquí la línea.
* |purchase_date|: Fecha de cuando se compró el activo
* |value|: Valor del activo en la fecha inicial de la amortización
* |residual_value|: Valor del activo en la fecha final de la amortización.
* |start_date|: Fecha en que se realizará el primer apunte de amortización.
* |end_date|: Fecha en que se terminará la amortización del activo. Si hemos
  rellenado, al crear el producto, el número de meses que durará la amortización,
  este campo se calculará en función de la fecha inicial, aunque podremos
  modificarlo.

Para poder introducir más información en el nuevo activo, seleccionaremos la
pestaña *Información adicional* y tendremos acceso a los siguientes campos:

* |company|: Donde indicaremos a cuál de nuestras empresas corresponde el activo que
  estamos introduciendo. 

* |method|: Si seleccionamos el método *Lineal* las cantidades de la amortización
  serán iguales durante todos los periodos.

* |frequency|: Seleccionaremos aquí si queremos que la frecuencia sea mensual o anual.

* |move|: En caso de venta, se rellenará automáticamente el asiento contable en el
  que se indica la venta.

* |customer_invoice_line|: En caso de que facturemos la venta, se introducirá
  aquí automáticamente la línea en la que se factura.

Una vez rellenados todos los campos, o como mínimo, todos los obligatorios, podremos
clicar en el botón *Crear líneas* de la pestaña *Líneas* y se nos generarán la líneas de
amortización según los parámetros que le hemos indicado. Hay que tener en cuenta
que en este punto, el activo sigue en estado *Borrador*, por lo que todavía podríamos realizar
modificaciones, borrar las líneas y volver a crearlas siguiendo parámetros distintos.
Una vez estén generadas las líneas de activo, podemos confirmar el plan de amortización
utilizando el botón *ejecutar*. A partir de este momento se fijarán las líneas y ya no se
podrán modificar.


Creación desde facturas
=======================
Si hemos generado una factura de proveedor por la compra del activo e introducimos
en el campo |supplier_invoice_line| una línea por esta factura, el programa se
encargará de rellenar todos los datos del activo a partir de la línea de factura.
Los campos que se rellenarán son los siguientes:

* |purchase_date|: Se utilizará el campo |invoice_date| de la factura.
* |value|: Se utilizará el |invoice_amount| de la línea de factura
* |quantity|: Se utilizará la |invoice_quantity| de la línea de factura.
* |unit|: Se utilizará la |invoice_unit| de la línea de factura


Procesar amortizaciones
=======================
Una vez creadas las líneas sobre del plan de amortización podemos empezar a procesar
la amortización. Este proceso consiste en asentar las líneas que ya han vencido 
generando los apuntes correspondientes a cada línea.

Para ello accederemos al menú |menu_create_moves| y se nos abrirá un asistente donde
deberemos indicar hasta que fecha queremos que se procese la amortización.
Los apuntes que se generen se crearán en estado confirmado. Podemos consultar los
apuntes creados en las líneas de las amortizaciones.


Actualización de activos
========================

En caso de que queramos realizar cualquier cambio en el valor del activo, el valor
residual o la fecha final de la amortización, podemos hacerlo por medio del
botón *Actualizar activo* y se nos abrirá una ventana donde podremos
seleccionar los nuevos valores para el activo. Una vez modificados los valores
se recalcularán las líneas de de amortización con los nuevos valores.

.. note::
   Este proceso no modificará las líneas ya asentadas o procesadas, sino que sólo 
   afectará a las líneas pendientes de amortizar.


Finalización de activos
=======================

Podemos finalizar la amortización de un activo utilizando el botón *Cerrar* de la
pantalla de activos. Antes de finalizar un activo debemos asegurarnos de haber generado
todos los apuntes de amortización pendiente ya que este proceso eliminará todas las
líneas que no hayan sido asentadas o procesadas en el momento del cierre, y generará
un apunte reflejando el cierre del mismo con que quedaba pendiente de amortizar.
En caso de perder el activo, o que este sea substraído, la finalización del activo se 
deberá de realizar sin asentar las líneas posteriores a la pérdida o substracción, de 
esta manera la pérdida del activo se reflejará contablemente con un apunte por el 
total de las líneas que quedaban por amortizar.

Contablemente se recomienda no finalizar ningún activo hasta que no dejemos
de disponer de él (ya sea porque prescindamos de él, haya sido substraído o dejado
de funcionar, etc) y no cuando se finaliza la amortización.
Esto se debe a que una vez finalizado, el activo no se puede modificar
y si sufre alguna revalorización o actualización no podríamos reflejarlo en la ficha
del activo.


Venta de activos
================

Una vez iniciada la amortización del activo puede ser que tengamos la necesidad o
la oportunidad de venderlo. Para ello accedemos al menú *facturas* por medio de la
ruta: |invoice_menu| y generamos una nueva factura clicando en el botón *Nuevo*.
Se nos abrirá la ficha de edición de factura y deberemos rellenar los
campos obligatorios (|party_inv|, |journal_inv|, |payment_term_inv| y
|currency_inv|) e indicar en las |lines_inv| de la factura el activo que queremos
vender.

Para ello clicaremos en el botón *Nuevo registro* en la sección |lines_inv| y se nos abrirá
una ventana flotante en la que tendremos que elegir en |product_inv| el tipo de activo que
queremos vender. Una vez hecho aparecerá, inmediatamente debajo de |product_inv|, el campo
|asset_inv| donde tendremos que seleccionar el activo concreto que queremos vender (en caso
de querer vender un vehículo por ejemplo, en |product_inv| seleccionaríamos la plantilla
de producto *Vehículo* y en |asset_inv| el vehículo en cuestión que queremos vender).
Con la selección del activo en el campo |product_inv| también se nos habrá rellenado
automáticamente el campo |account_inv| con la cuenta 77100000 (*Beneficios procedentes
del inmovilizado material*). Deberemos rellenar los campos obligatorios |quantity| y
|unit_price| y generar el campo para el impuesto en caso necesario. Aceptamos y se nos
cerrará la ventana flotante.

Una vez rellenados todos los campos podemos validar la factura y posteriormente
confirmarla.

.. Note::
   Si tenemos muchos productos del mismo tipo, al seleccionar el que queremos vender
   podemos fijarnos en el número de referencia para asegurarnos de que hacemos la factura sobre
   el activo que queremos vender.

Al confirmar la factura si accedemos a la ficha del activo observaremos que las líneas
de amortización que no se habían hecho efectivas han desaparecido y solo quedan aquellas
que ya han sido asentadas y el estado del activo es *Cerrado*.

Si accedemos a la pestaña *Información adicional* y clicamos con el botón derecho en el
campo |move_inv| y seleccionamos *Editar*, accederemos a la pestaña de los asientos
contables con los apuntes que se han generado.

Una vez generada la factura se realizará el apunte para esta venta en la cuenta 7710000
*Beneficios procedentes del inmovilizado material* con el valor restante del activo.

.. Note::
   Para reflejar la pérdida, en caso de que se venda por debajo de su valor, se deberá
   crear un asiento manual por la diferencia entre el valor del activo en la fecha de
   la venta y el precio de venta para cuadrar los importes.

.. |depreciable| field:: product.template/depreciable
.. |product| field:: account.asset/product
.. |account_journal| field:: account.asset/account_journal
.. |supplier_invoice_line| field:: account.asset/supplier_invoice_line
.. |value| field:: account.asset/value
.. |residual_value| field:: account.asset/residual_value
.. |purchase_date| field:: account.asset/purchase_date
.. |start_date| field:: account.asset/start_date
.. |end_date| field:: account.asset/end_date
.. |supplier_invoice_line| field:: account.asset/supplier_invoice_line
.. |unit| field:: account.asset/unit
.. |quantity| field:: account.asset/quantity
.. |company| field:: account.asset/company
.. |method| field:: account.asset/depreciation_method
.. |frequency| field:: account.asset/frequency
.. |move| field:: account.asset/move
.. |customer_invoice_line| field:: account.asset/customer_invoice_line
.. |invoice_unit| field:: account.invoice.line/unit
.. |invoice_quantity| field:: account.invoice.line/quantity
.. |invoice_amount| field:: account.invoice.line/amount
.. |invoice_date| field:: account.invoice/invoice_date
.. |invoice_menu| tryref:: account_invoice.menu_invoice_out_invoice_form/complete_name
.. |party_inv| field:: account.invoice/party
.. |journal_inv| field:: account.invoice/journal
.. |payment_term_inv| field:: account.invoice/payment_term
.. |currency_inv| field:: account.invoice/currency
.. |lines_inv| field:: account.invoice/lines
.. |product_inv| field:: account.invoice.line/product
.. |asset_inv| field:: account.invoice.line/asset
.. |account_inv| field:: account.invoice.line/account
.. |quantity| field:: account.invoice.line/quantity
.. |unit_price| field:: account.invoice.line/unit_price
.. |menu_asset| tryref:: account_asset.menu_asset_form/complete_name
.. |menu_create_moves| tryref:: account_asset.menu_create_moves/complete_name
.. |move_inv| field:: account.asset.line/move
