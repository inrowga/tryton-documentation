=========
Productos
=========

El concepto de producto en Tryton está compuesto de dos modelos: la plantilla
de producto y el producto. Esta separación se usa para poder definir
variantes de un producto (por ejemplo: tallas, colores...) definiendo los datos
compartidos en la *plantilla* y los específicos en el *producto*.

.. inheritref:: product/product:section:producto

Producto
========

.. view:: product.template_view_form
   :field: name

.. inheritref:: product/product:bullet_list:template_fields

* |name|
* |type| Las opciones por defecto son: bienes, activos y servicios.
* |category|. La categoría principal del producto.
* |list_price|. Precio de venta.
* |cost_price|. Precio de coste.
* |cost_price_method|. Método del precio del coste
* |default_uom|. La unidad de medida por defecto para este
  producto, usado por ejemplo para expresar niveles de stock.
* |active|. Activar o desactivar el producto sin borrarlo.

.. |name| field:: product.template/name
.. |type| field:: product.template/type
.. |category| field:: product.template/category
.. |list_price| field:: product.template/list_price
.. |cost_price| field:: product.template/cost_price
.. |cost_price_method| field:: product.template/cost_price_method
.. |default_uom| field:: product.template/default_uom
.. |active| field:: product.template/active

Por cada plantilla, podrá crear sus variantes. Si no trabaja con variantes, este paso
será transparente para vosotros:

.. inheritref:: product/product:bullet_list:product_fields

* |code|
* |description|

.. |code| field:: product.product/code
.. |description| field:: product.product/description

.. inheritref:: product/product:section:calculo_precio_coste

¿Cómo se calcula el precio de coste?
====================================

El campo |cost_price_method| determina cómo se calcula el |cost_price|  de
cada producto. Los posibles métodos son:

.. inheritref:: product/product:bullet_list:cost_price_method_options

* Fijo
* Promedio

Cómo se explica en el apartado :ref:`product-multicompany` tanto
el |cost_price| cómo el |cost_price_method| pueden ser distintos para cada
empresa.


Método de coste Fijo
~~~~~~~~~~~~~~~~~~~~

Se establece el valor manualmente en la ficha de producto y éste no se
actualiza automáticamente bajo ninguna circunstancia.

Método de coste Promedio
~~~~~~~~~~~~~~~~~~~~~~~
Cuando se realiza un albarán de proveedor (o una devolución a proveedor) se
recalcula el precio de coste del producto de forma ponderada; sumando (o
restando) el precio al que se ha comprado teniendo en cuenta la cantidad que
se está moviendo respecto al stock total de este producto en nuestro almacén
(Precio Medio Ponderado - PMP). Cuando se realiza una producción también se
recalcula el precio de coste de los productos producidos sumando, de forma
ponderada, el coste unitario de la producción.

Aunque se elija esta opción aún se podrá establecer el precio de coste de
forma manual. Si hacemos esto estaremos indicando al sistema que las unidades
de este producto que hay en nuestro almacén tienen el precio de coste unitario
que indicamos y la próxima vez que se recalcule se tomará de base este precio
de coste.


.. inheritref:: product/product:section:categoria

Desactivar productos
====================

A veces es necesario poder desactivar un producto porqué ya no trabajamos con
el mismo, pero esto no es posible porqué ya tenemos algún documento (factura,
presupuesto, etc) que hace referencia al mismo.

En este caso podremos desactivarlo tal cómo se explica en
:ref:`desactivar-registros`.

Clasificar los productos
========================

Los productos se pueden asociar a una categoria. Entonces podemos utilizar la
opción |menu_product_categories| para consultar todos los productos de una
categoria. Para ello, simplemente hace falta hacer doble clic sobre la
categoría y se nos abrirá el listado de todos los productos de la misma.

.. |menu_product_categories| tryref:: product.menu_category_tree/complete_name


.. _product-multicompany:

Trabajar con productos en multicompañía
=======================================

Por defecto todos los productos se comparten entre la compañías. Esto significa
que si creamos un producto en la empresa A, también lo veremos disponible en la
empresa B. A pesar que los productos que vemos sean los mismos, no todos los
datos de un determinado producto son los mismos en todas las compañías.

Por ejemplo, podemos entrar en la compañía A y definir un precio de venta
para el producto y después entrar en la compañía B y ahí definir otro precio
de venta.

A continuación detallamos los campos que dependen de la compañía:

.. inheritref:: product/product:bullet_list:multicompany_fields

* |list_price|
* |cost_price|
* |cost_price_method|

.. inheritref:: product/product:section:precio_de_venta

Precio de venta
===============

Si usaremos el precio de venta de la ficha del producto como precio de venta,
no hace falta instalar ni configurar nada más. Para todos los clientes se le
aplicará este precio de venta.

.. inheritref:: product/product:section:unidades_de_medida

Unidades de medida
==================

.. inheritref:: product/produc:toctree:otros_modelos

.. toctree::
   :maxdepth: 2

   unit_of_measure
