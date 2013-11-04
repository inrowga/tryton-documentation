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

* Abra el menú |menu_template|
* Haga clic en la pestaña **Lotes**
* Introduzca el *Tipo de lote*

Esto hará que cuando se procese un albarán (movimiento) sea obligatorio un lote
dependiendo del tipo de lote en el producto. Por ejemplo, si a un producto añado
que sea obligado un lote en "cliente", cuando realize un albarán de salida (a cliente)
deberé añadir un lote. En cambio, cuando sea un albarán de proveedor no hará falta
ya que en el producto no le hemos marcado un lote requerido de proveedor.

.. |menu_template| tryref:: product.menu_template/complete_name

.. inheritref:: stock_lot/stock_lot:section:anadir_lote_a_movimiento

Añadir lote a movimiento
------------------------

Para añadir un lote a un movimiento de stock siga los siguientes pasos:

* Abra el menú **Logística** y el tipo de albarán correspondiente al que quiera
  añadir el lote (proveedor, cliente, interno).
* Busque y abra el albarán concreto a añadir el lote.
* Abra cada línea de albarán (movimiento), e introduzca el lote en el campo
  correspondiente.
