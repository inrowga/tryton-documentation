#:inside:party/party:section:terceros-multicompania#

* |account_payable|
* |account_receivable|
* |customer_tax_rule|
* |supplier_tax_rule|

.. |account_payable| field:: party.party/account_payable
.. |account_receivable| field:: party.party/account_receivable
.. |customer_tax_rule| field:: party.party/customer_tax_rule
.. |supplier_tax_rule| field:: party.party/supplier_tax_rule


#:inside:party/party:section:crear-un-tercero#


En la pestaña Contabilidad, se puede definir |account_payable| y la
|account_receivable| que se utilizarán cómo cuentas a cobrar/pagar por defecto
en las facturas relacionadas con el tercero. Además podremos definir la
|customer_tax_rule| y la |supplier_tax_rule|, para especificar una regla de
impuestos que se aplique al tercero.

.. hint:: Si tenemos clientes/proveedores intracomunitarios, podemos utilizar
          la regla de impuestos Régimen Intracomunitario para que el sistema nos
          aplique automáticamente los impuestos intracomunitarios para las facturas
          que se creen para este cliente.

.. |receivable| field:: party.party/receivable
.. |receivable_today| field:: party.party/receivable_today
.. |payable| field:: party.party/payable
.. |payable_today| field:: party.party/payable_today
