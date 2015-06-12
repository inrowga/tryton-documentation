#:inside:product/product:bullet_list:multicompany_fields#

* |account_revenue|
* |account_expense|


#:before:product/product:section:pestanas#

En la pestaña **Contabilidad** podremos especificar la configuración contable
del producto, pudiendo especificar la |account_revenue| y la |account_expense|.
Además podremos indicar también qué impuestos se aplicarán por defecto al
producto al venderlo, en el campo |customer_taxes|, y al comprarlo, en el campo
|supplier_taxes|. Por ejemplo, podríamos utilizar los siguientes valores para
estos campos:

* |account_revenue|: 700000 - Ventas de mercaderías en España.
* |account_expense|: 600000 - Compras de mercaderías.
* |customer_taxes|: IVA 21%
* |supplier_taxes|: 21% IVA Soportado (operaciones corrientes)

Para simplificar la configuración contable de los productos, podemos marcar
los campos |account_category| y |taxes_category| para que se le aplique
al producto la |account_revenue|, la |account_expense|, los |customer_taxes| y
los |supplier_taxes| definidos en la |category| del producto que hayamos
seleccionado en la pestaña anterior. En :ref:`cat-productos` podemos ver
como configurar la contabilidad de las categorías.


#:before:product/product:section:unidades_de_medida#

Desde la pestaña **contabilidad** podremos indicar la |cat_account_revenue| y
la |cat_account_expense|, así como los |cat_supplier_taxes| y los
|cat_customer_taxes| por defecto que se utilizarán en la |category|. De esta 
forma, cuando configuremos un producto podremos indicarle que utilice las
cuentas e impuestos por defecto de la categoría a la que pertenece, y
simplificar así nuestra tarea. En caso de que en el producto se indiquen unas
cuentas o unos impuestos distintos a los de la categoría a la que pertenece,
los indicados en la categoría del producto no tendrán efecto.

.. |account_revenue| field:: product.template/account_revenue
.. |account_expense| field:: product.template/account_expense
.. |customer_taxes| field:: product.template/customer_taxes
.. |supplier_taxes| field:: product.template/supplier_taxes
.. |account_category| field:: product.template/account_category
.. |taxes_category| field:: product.template/taxes_category
.. |cat_account_revenue| field:: product.category/account_revenue
.. |cat_account_expense| field:: product.category/account_expense
.. |cat_supplier_taxes| field:: product.category/supplier_taxes
.. |cat_customer_taxes| field:: product.category/customer_taxes
.. |category| field:: product.template/category