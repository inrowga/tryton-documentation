Facturación de proyectos
========================

Desde los proyectos podrá crear una factura a partir del tiempo de:

.. inheritref:: project_invoice/project_invoice:bullet_list:project_invoice_method

* Por el esfuerzo estimado
* Por las horas realitzadas

En el proyecto, dispondremos del campo |invoice_method| donde decidimos el
proyecto y el tipo de facturación.

.. |invoice_method| field:: project.work/project_invoice_method

.. inheritref:: project_invoice/project_invoice:section:esfuerzo_estimado

Por el esfuerzo estimado
------------------------

Si seleccionamos esta opción podemos crear una factura con el tiempo estimado. Para
que se active el botón *Facturar* deberá que todos los proyectos y tareas relacionados
con el proyecto padre esten en el estado realizado.

.. inheritref:: project_invoice/project_invoice:section:horas_realizadas

Por las horas realizadas
------------------------

Si seleccionamos esta opción se activará el botón *Facturar* donde podremos crear
una factura a partir de las horas estimadas del proyecto.

.. inheritref:: project_invoice/project_invoice:section:factura

Factura
-------

Para poder realizar esta acción de *Facturar* deberá que todos los proyectos como
sus tareas dispongan de la siguiente información:

* Producto y cuenta de ingresos asociado al producto.
* Tercero y plazo de pago asociado al cliente.

Una vez accionamos el botón de *Facturar* se nos creará una nueva factura. Podemos
acceder a ellas en el botón de registros relacionados a este proyecto.

Una vez el proyecto se ha facturado, ya no puede volver a facturar ese proyecto.
Para volver a facturar deberá eliminar la factura generada. En el caso que la factura
borrador se haya confirmado, ya no podrá facturar mas a partir del proyecto.

Las líneas de la factura quedarán anotado la siguiente información:

* Producto relacionado con el proyecto o tarea.
* Descripción del proyecto o tarea.
