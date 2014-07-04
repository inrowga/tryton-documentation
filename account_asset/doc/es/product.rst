#:after:product/product:section:crear-variantes#


.. _product-para-amortizacion-de-activos:

Crear un producto para la amortización de activos
=================================================

Para poder contabilizar activos y su amortización es necesario definir productos
de tipo "Activo" y en la pestaña "Contabilidad" marcar la casilla
|depreciable| y obligatoriamente siguientes cuentas contables:

* |account_asset|:  Será utilizada por la factura de proveedor para anotar
  la compra del activo.
* |account_depreciation|**: Donde se anota la depreciación del activo.
* |account_expense|: Cuenta dónde se anota la depreciación cómo gasto.

Además opcionalmente podemos indiciar la |account_revenue| que se utilizará
para reflejar los posibles ingresos generados por la venta del activo (en
función de la depreciación ya realizada y el precio de venta).

Si sabemos el número de meses en que se consideran cómo amortizados los
activos, lo podemos indicar en el campo |depreciation_duration|

Por ejemplo podemos utilizar los siguientes valores:

* |account_asset|: 213000 - Maquinaria
* |account_depreciation|: 281300 - Amortización acumulada de maquinaria
* |account_expense|: 681000 - Amortización del inmovilizado material
* |account_revenue|: 771000 - Beneficios procedentes del inmovilizado material

.. |depreciable| field:: product.template/depreciable
.. |account_asset| field:: product.template/account_asset
.. |account_depreciation| field:: product.template/account_depreciation
.. |account_revenue| field:: product.template/account_revenue
.. |account_expense| field:: product.template/account_expense
.. |depreciation_duration| field:: product.template/depreciation_duration
