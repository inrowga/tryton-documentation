#:after:product/procduct:paragraph:tipo-producto#

Además, si indicamos que el |type| es *Activos*, en la pestaña
*Contabilidad* se nos habilitará un campo para indicar si este bien es 
|depreciable|.


#:after:product/product:section:crear-variantes#

.. _product-para-amortizacion-de-activos:

Crear un producto para la amortización de activos
=================================================

Para poder contabilizar activos y su amortización es necesario definir productos de
tipo "Activo", por lo que tendremos que crear un nuevo producto indicándole que es
tipo *Activo* y en la pestaña *Contabilidad* marcar la casilla |depreciable|.
Además, también deberemos indicar las siguiente cuentas contables,
de las cuales las dos primeras son obligatorias:

* |account_asset|:  Es la cuenta que será utilizada por la factura de proveedor
  para anotar la compra del activo. *Como por ejemplo la cuenta 213000 - Maquinaria.*

* |account_depreciation|: Es la cuenta donde se anota la depreciación del activo
  en el haber, y el gasto en el debe de la cuenta de gastos. *Como por ejemplo la cuenta
  281300 - Amortización acumulada de maquinaria*.

* |account_revenue|: Se utilizará para reflejar los posibles ingresos generados
  por la venta del activo (en función de la depreciación ya realizada y el precio de
  venta).
  *Como por ejemplo la cuenta 771000 - Beneficios procedentes del inmovilizado material*.

* |account_expense|:  Ee utilizará para reflejar las posibles pérdidas generados por
  la venta del activo (en función de la depreciación ya realizada y el precio de venta).
  *Como por ejemplo la cuenta 681000 - Amortización del inmovilizado material.*


Si sabemos el número de meses en que se consideran cómo amortizados los
activos, lo podemos indicar en el campo |depreciation_duration|.

El producto sirve solamente de plantilla y para que el sistema pueda obtener en qué
cuentas contables debe realizar los apuntes. No es necesario, por tanto, crear un nuevo
producto para  cada ítem que queramos amortizar, solamente lo tendremos que hacer si
queremos cambiar alguna de las cuentas que intervienen en la compra, amortización o venta.

Por ejemplo, podemos tener un sólo producto *Vehículo* y disponer de varios vehículos a
amortizar en la empresa, siempre y cuando deseemos que todos utilicen la misma cuenta
de activo, de amortización, de gastos y de ingresos (en caso que lo vendamos).

.. |type| field:: product.template/type
.. |depreciable| field:: product.template/depreciable
.. |account_asset| field:: product.template/account_asset
.. |account_depreciation| field:: product.template/account_depreciation
.. |account_revenue| field:: product.template/account_revenue
.. |account_expense| field:: product.template/account_expense
.. |depreciation_duration| field:: product.template/depreciation_duration
