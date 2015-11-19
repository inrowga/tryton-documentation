#:after:account/account:paragraph:secuencias#

Por otro lado, **Tryton** permite utilizar la misma secuencia de facturas para
las facturas de cliente, proveedor, abonos de cliente y abonos de proveedor
pero esto no es válido bajo la normativa española. Así que, si nuestra empresa
se rige por esta legislación, deberemos crear una serie exclusiva para nuestra
facturación.


#:after:account/account:section:impuestos#

.. _configurar-plazos:

Configurar plazos de pago
-------------------------

Para crear o configurar los plazos de pago que posteriormente podremos aplicar
a nuestros clientes o proveedores, accederemos a
|menu_payment_terms_configuration| y, tras clicar en *Nuevo*, se nos abrirá el
formulario de edición de los plazos de pago. En él deberemos
indicar un nombre y rellenar al menos una línea de plazo de pago. Hay que tener
en cuenta que cada plazo de pago se compone de una o varias |lines|, estas
|lines| nos indicarán cuándo y cómo se realizará el pago. Además, la cantidad
de |lines| que compongan el plazo nos indicará cuántos pagos se deberán hacer.
Por ejemplo, si un pago es a 30 días, este plazo de pago sólo tendrá una
línea, en cambio, si el plazo de pago se realiza a 15 y a 30 días, se deberán
crear dos líneas, una para el pago a 15 días y otra para el pago a 30 días.

Cuando accedamos a crear una nueva línea, los campos que tendremos que
rellenar son:

* |type|: Donde podemos escoger entre:

    * *Fijo*: Es un valor fijo, siempre será el mismo sea cual sea el importe
      total a pagar, por lo que no dependerá de nada. Al seleccionar esta
      opción aparecerán dos campos nuevos:
      
           * |amount|: Indicaremos el importe fijo que se deberá de pagar.
           * |currency|: La moneda que se usará para realizar el pago.
           
    * *Porcentaje sobre remanente*: Calculará el importe a pagar según un
      porcentaje aplicado sobre la cantidad que queda pendiente de pago.
    * *Porcentaje sobre total*: Calculará el importe a pagar según un
      porcentaje sobre el valor total de la factura. Al seleccionar esta opción
      o la anterior aparecerán dos campos nuevos:
      
           * |percentage|: Indicaremos aquí el valor en % de 0 a 100 que
             queremos que se aplique al total o al remanente.
           * |divisor|: Este campo se nos rellenará automáticamente si
             indicamos previamente el |percentage|. En caso de rellenar este
             campo primero, el que se rellenará automáticamente será el campo
             |percentage|. Esto se debe a que ambos campos están relacionados e
             indican lo mismo pero desde distintos puntos de vista. En este
             campo podremos indicar el divisor que se utilizará para realizar
             el cálculo del importe, o, dicho de otro modo, deberemos indicar
             por qué número queremos que se divida el total o remanente para
             calcular el importe a pagar. Por ejemplo, si indicamos en el campo
             |percentage| que se calcule sobre el 50 %, el campo |divisor| se
             nos rellenará con el número 2, ya que es lo mismo aplicar el 50 %
             a un importe que dividirlo por 2.
             
    * Remanente: El total de lo que queda por pagar, le resta del total lo ya
      pagado. Siempre que configuremos los plazos con una sola línea, deberemos 
      escoger esta tipología, ya que al no haber ningún pago previo se realizará
      el pago sobre el total. Además, cuando creemos plazos con varias |lines|,
      la última siempre deberá ser de esta tipología.
      
* |months|, |weeks| y |days|: Indicaremos cuántos meses, semanas y días pasarán
  para generar el pago de la línea del plazo que estamos creando.
* |month|, |weekday| y |day|: Indicaremos el mes, día de la semana o día del
  mes exacto en el que se realizará el pago de esta línea.

Veamos algunos ejemplos de cómo configurar estas |lines|:

* **Pago a 30 días**. Sólo crearemos una línea:

  * |type|: Remanente
  * |months|: 0
  * |weeks|: 0
  * |days|: 30

* **Pago a 15/30 días**. Crearemos dos líneas:

  * Primera línea:

    * |type|: Porcentaje sobre total
    * |percentage|: 50
    * |divisor|: 2
    * |months|: 0
    * |weeks|: 0
    * |days|: 15

  * Segunda línea:

    * |type|: Remanente
    * |months|: 0
    * |weeks|: 0
    * |days|: 30

* **Pago el 1 de cada mes**. Crearemos una línea:

    * |type|: Remanente
    * |day|: 1
    * Dejaremos el resto de campos a 0.

Podemos especificar para cada tercero un plazo de pago desde la pestaña
**Contabilidad** de la ficha del propio tercero. En ella podremos indicar los
plazos para las ventas (cliente) y para las compras (proveedor) que le
realicemos.


.. |menu_payment_terms_configuration| tryref:: account_invoice.menu_payment_terms_configuration/complete_name
.. |lines| field:: account.invoice.payment_term/lines
.. |type| field:: account.invoice.payment_term.line/type
.. |amount| field:: account.invoice.payment_term.line/amount
.. |currency| field:: account.invoice.payment_term.line/currency
.. |percentage| field:: account.invoice.payment_term.line/percentage
.. |divisor| field:: account.invoice.payment_term.line/divisor
.. |months| field:: account.invoice.payment_term.line/months
.. |weeks| field:: account.invoice.payment_term.line/weeks
.. |days| field:: account.invoice.payment_term.line/days
.. |month| field:: account.invoice.payment_term.line/month
.. |weekday| field:: account.invoice.payment_term.line/weekday
.. |day| field:: account.invoice.payment_term.line/day
