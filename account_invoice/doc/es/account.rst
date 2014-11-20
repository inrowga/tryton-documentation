#:after:account/account:paragraph:secuencias#

Tryton permite utilizar la misma secuencia de facturas para las facturas de
cliente, proveedor, abonos de cliente y abonos de proveedor pero esto no es 
válido bajo la normativa española así que si nos regimos por esta legislación
deberemos crear una serie esclusiva para nuestra facturación.

#:before:account/account:section:asientos_y_movimientos#

Facturas
========

.. inheritref:: account/account:toctree:invoice

.. toctree::
   :maxdepth: 2

   account_invoice
