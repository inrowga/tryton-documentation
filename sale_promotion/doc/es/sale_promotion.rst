===================
Ventas. Promociones
===================

Las promociones nos permitirá crear condiciones para aplicar nuevos precios en
las líneas de una venta (ofrecer el producto con un nuevo precio).

.. inheritref:: sale_promotion/sale_promotion:section:configuracion

Configuración
=============

En configuración diseñaremos nuestra promociones. Una promoción consiste en dos partes:

* La condición para se aplique.
* El cálculo del nuevo precio.

En el caso que una venta se le aplique una condición de la promoción, en sus líneas, se aplicará
el nuevo precio definido en la promoción.

.. inheritref:: sale_promotion/sale_promotion:section:condicion

Condición
---------

La base de la condición se aplicar con los siguientes campos de la promoción:

* Fecha inicial/final: Rango de fechas para aplicar la condición. Si no se definen fechas, se aplicará siempre.
* Tarifa: Sólo se aplicará la condición si la venta dispone de la misma tarifa de venta.
* Cantidad: Unidades del producto en que se aplicará la promoción (igual o superior).
* Productos: productos que se aplicará la promoción. Si no se indica productos, se aplicará siempre en todos los productos.

.. inheritref:: sale_promotion/sale_promotion:section:precio

Precio
------

Mediante el campo "Fórmula" definiremos el nuevo precio de la línea de venta (se aplicará la promoción).

Ejemplo:

Aplicar un 10% de descuento: unit_price*0.9


.. inheritref:: sale_promotion/sale_promotion:section:venta

Venta
=====

Estados
-------

* En el momento que un pedido de venta pasa al estado "Presupuesto",
  se aplicarán las promociones que se cumplen.
* En el momento que un pedido de venta pasa otra vez al estado de "Borrador", 
  se anularán las promociones que se han aplicado y restableciendo de nuevo el precio
  actual del producto.
