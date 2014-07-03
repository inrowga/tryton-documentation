==========
Secuencias
==========

Las secuencias son las numeraciones de ciertos objetos que se le asignaran
automáticamente.

.. tip:: Una numeración correlativa de facturas, pedidos de venta, etc

Para diseñar nuestra numeración podemos acceder a:

* **Administración/Secuencias/Secuencias**'

Por ejemplo, en las secuencia de facturas, dispondremos de:

* **Facturas cliente:** Account Invoice In
* **Facturas proveedor:** Account Invoice Out

En una secuencia, disponemos de los valores:

* **Prefijo:** Podemos hacer uso de expresiones como ``%{year}``
* **Dígitos de relleno:** La cantidad de números que dispondremos: 001
* **Cantidad a incrementar:** El próximo número a dar de alta
* **Sufijo:** Si queremos un identificador, por ejemplo V de pedido de venta.
* **Siguiente número**

.. warning:: En el caso de Nereid o entorno web se recomineda que la numeración de
               pedidos de venta, facturas, albaranes o cualquier modelo no incluya
               la barra **/** para no confundir con las urls de la web (direcciones).
