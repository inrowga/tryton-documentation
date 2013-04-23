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

El método del precio del coste:

.. inheritref:: product/product:bullet_list:cost_price_method_options

* Fijo: El precio de coste permanece sin cambios
* Media: El precio de coste es la media de coste de todos los elementos que hay en stock

Por cada plantilla, podrá crear sus variantes. Si no trabaja con variantes, este paso
será transparente para vosotros:

.. inheritref:: product/product:bullet_list:product_fields

* |code|
* |description|

.. |code| field:: product.product/code
.. |description| field:: product.product/description

.. inheritref:: product/product:section:categoria

Categoría
=========

La categoría de producto está compuesta de un nombre. Las categorías de
productos se organizan en estructura de arbol.

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
