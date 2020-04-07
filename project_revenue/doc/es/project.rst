#:before:project/project:section:estados#

Costes de los proyectos y tareas
================================

A proyectos y tareas disponemos de dos nuevos campos para el cálculo de los costes:

* Product. Debe ser un producto del tipo servicio y una unidad de media del tipo tiempo.
* Precio de venta

Cuando seleccionamos un producto se le asignará el precio de venta en el proyecto
o tarea que disponga de este producto. Este precio en el proyecto o tarea lo podemos
modificar si nos interesa aplicar otro precio distinto al precio de venta del producto.

A partir del precio del proyecto o tarea disponemos de dos nuevos campos que nos
calcularan información sobre:

* Coste: El coste se calcula a partir de las horas destinadas en la tarea por
  el coste del empleado (definido en su ficha)
* Ingresos: Se calcula a partir del precio de la tarea por las horas del
  *Esfuerzo total*. Sólo se calcula si se el trabajo es una **tarea** y se dispone
  de precio.

.. note:: Para el cálculo del coste deberá a sus empleados añadir el precio del
          coste de los empleados al menu empleados.

