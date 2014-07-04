#:inside:product/product:bullet_list:multicompany_fields#

* |account_revenue|
* |account_expense|

.. |account_revenue| field:: product.template/account_revenue
.. |account_expense| field:: product.template/account_expense
.. |customer_taxes| field:: product.template/customer_taxes
.. |supplier_taxes| field:: product.template/supplier_taxes


#:before:product/product:section:crear-variantes#

En la pestaña Contabilidad podremos especificar la configuración contable del
producto. Así podremos especificar la |account_revenue| y la |account_expense|.
Además podremos especificar que impuestos se aplicarán por defecto para el
producto en ventas en el campo |customer_taxes| y para compras en el campo
|supplier_taxes|.

.. tip:: En los impuestos por defecto podemos seleccionar más de un valor
    en caso de que sea necesario.

Por ejemplo podemos utilizar los siguientes valores:

* |account_revenue|: 700000 - Ventas de mercaderías en España.
* |account_expense|: 600000 - Compras de mercaderías.
* |customer_taxes|: IVA 21%
* |supplier_taxes|: 21% IVA Soportado (operaciones corrientes)

Para simplificar la configuración contable de los productos, podemos marcar
el campo |account_category| y el campo |taxes_category| para que se cojan la
|account_revenue|, la |account_expense|, los |customer_taxes| y los
|supplier_taxes| definidos en la categoría.

.. |account_category| field:: product.template/account_category
.. |taxes_category| field:: product.template/taxes_category




