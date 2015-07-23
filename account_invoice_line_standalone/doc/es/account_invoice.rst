#:before:account_invoice/account_invoice:section:cancelar#

.. inheritref:: account_invoice_line_standalone/account_invoice:section:lineas_pendientes_de_facturar

------------------------------------
Añadir líneas pendientes de facturar
------------------------------------

En sistemas de automatización de facturación se generan facturas a partir de
líneas a facturar. Esto es muy común por ejemplo en el proceso de contratos de
servicios que se generen líneas, y al fin de mes, se facturen.

.. image:: images/account_invoice_standalone.png

.. inheritref:: account_invoice_line_standalone/account:paragraph:cuando_crea_una_factura

Cuando creas un nueva factura, al seleccionar el tercero, en las líneas de la
factura, podrás seleccionar líneas existentes pendientes de facturar.

.. note:: Sólo podrás seleccionar las líneas de factura del tercero de la
   factura y que no sean facturadas previamente.
