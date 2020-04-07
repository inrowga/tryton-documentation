#:after:party/party:paragraph:sale#

El campo método agrupación albaranes de venta nos permite definir cómo se van a agrupar los 
albaranes que se generen por las ventas de este tercero. Los métodos disponibles
son los siguientes:

.. inheritref:: party/party:bullet_list:sale_shipment_grouping_method

* **Ninguno**: Las facturas no se van a agrupar y se generará una factura
  para cada venta
* **Estándard**: Las líneas de factura de esa venta se añadirán a las facturas
  en estado Borrador existentes.

.. |grouping_method| field:: party.party/sale_shipment_grouping_method 
