=====
Lotes
=====

El módulo **Lotes** define lotes de producto.

Un lote, por defecto, simplemente es un número para etiquetar movimientos.
Cuando es necesario seleccionar el tipo de ubicación involucrado en un
movimiento es posible definir lotes por producto.

.. inheritref:: stock_lot/stock_lot:section:creacion_de_un_lote

Creación de un lote
-------------------

Para añadir un nuevo lote a Tryton siga los siguientes pasos:

* Abra el menú |menu_lot_form|
* Haga clic en el botón nuevo lote
* Introduzca el número de lote y el producto

.. |menu_lot_form| tryref:: stock_lot.menu_lot_form/complete_name

.. inheritref:: stock_lot/stock_lot:section:lote_requerido

Lote requerido
--------------

Para indicar que un producto determinado debe tener asignado obligatoriamente
un lote, siga los siguientes pasos:

* Abra el menú |menu_product_product|
* Haga clic en la pestaña **Lotes**
* Introduzca el *Tipo de lote*

.. |menu_product_product| tryref:: product.menu_product_product/complete_name

.. inheritref:: stock_lot/stock_lot:section:anadir_lote_a_movimiento

Añadir lote a movimiento
------------------------

Para añadir un lote a un movimiento de stock siga los siguientes pasos:

* Abra el menú **Logística** y el tipo de albarán correspondiente al que quiera
  añadir el lote (proveedor, cliente, interno).
* Busque y abra el albarán concreto a añadir el lote.
* Abra cada línea de albarán (movimiento), e introduzca el lote en el campo
  correspondiente.
