.. inheritref:: account_asset/account_asset:section:activos

Activos
=======

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

Una vez hecha la compra (factura de proveedor) se puede dar de alta el activo en el menú
|menu_asset| indicando el producto (por ejemplo Maquinaria) y la línea de la factura de compra.
Se rellenan de forma automática los campos Valor, Fecha inicial, Fecha final, aunque es posible
ajustarlos y también definir el Valor residual, el Método de amortización y la Frecuencia
(sólo soporta amortización lineal, calculada mensualmente o anualmente). El botón
"Crear apuntes" permite calcular el cuadro de amortizaciones. Si con el tiempo cambian el Valor
del activo, el Valor residual o la Fecha final se puede recalcular el cuadro de amortización con
el botón "Actualizar activos".

El menú |menu_create_moves| permite ejecutar un asistente que calcule de forma automática los
asientos de amortización hasta una fecha dada (por defecto hoy).

.. |menu_asset| tryref:: account_asset.menu_asset/complete_name
.. |menu_create_moves| tryref:: account_asset.menu_create_moves/complete_name
