==========
Producción
==========

Las producciones se utilizan para la transformación de materias, por ejemplo
para la fabricación de una pieza (material finalizado) a través de la unión
de varios componentes.

.. inheritref:: production/production:section:producir_materiales

Producir materiales
===================

Para producir materiales debemos crear una orden de producción desde la opción
|menu_production_list|.

.. view:: production.production_view_form
   :field: code

Las ordenes de producción están formados por dos tipos de movimiento:

* |inputs|: En ellas introduciremos todos los productos que se necessitan
  **consumir** para realizar la producción.
* |outputs|: En ellas introduciremos los productos **resultantes** de la
  producción.

.. |menu_production_list| tryref:: production.menu_production_list/complete_name
.. |inputs| field:: production/inputs
.. |outputs| field:: production/outputs
.. |cost| field:: production/cost

En la parte inferior izquierda podremos observar en todo momento en qué estado
se encuentra la producción. Los pasos básicos son los siguientes y siguen este
orden::

    Solicitud > Borrador > En Espera > Reservado > En ejecución > Finalizado

A continuación se detallan cada uno de ellos:

* **Solicitud**: En este estado se crean las producciones generadas.
  automáticamente por el sistema para satisfacer necesidades.
* **Borrador**: Estado inicial en que se introducen las entrada y salidas
  previstas.
* **En espera**: La producción esta a la espera de recibir los productos
  necesarios para consumir sus entradas.
* **Reservado**: Todas las entradas han sido reservadas pero la producción
  aún no ha empezado.
* **En ejecución**: La producción esta en curso. Todas las entradas han sido
  consumidas y se están realizando las salidas.
* **Realizado**: La producción ha sido terminada y todos los productos de
  salida han estado realizados.
* **Cancelado**: La producción ha sido cancelada.

Costes de producción
--------------------

Una vez finalizada la producción, se calculan los costos de la misma y
estos se reparten en las |outputs|, rellenando así el precio unitario de las
|outputs|.

En la pestaña Información Adicional podremos ver el |cost| total de la
producción.

Consumo de materiales no previstos
----------------------------------
En cualquier estado de la producción podemos añadir nuevos materiales en las
|inputs| y las |outputs| de la producción, aunque no quitar las que ya
están realizados. Esto nos permite añadir entradas adicionales y salidas no
previstas, por ejemplo desechos, mientras la producción esta en curso.

Para introducir un desecho debemos introducir una nueva línea en las
|outputs| utilizando cómo ubicación destino una ubicación de tipo
Perdido/Encontrado para reflejar que hemos desechado esos productos.


.. inheritref:: company/company:section:lista_de_materiales

Lista de materiales
===================

.. _production-bom:

Las listas de materiales nos sirven para determinar la cantidad de materiales
necesaria para la producción de un determinado producto. Haciendo un símil
con el mundo de la cocina, las listas de materiales son las recetas que
nos describen como debemos realizar un determinado plato.

.. view:: production.bom_view_form
   :field: name

.. _production-create-bom:

Crear una lista de materiales
-----------------------------

Para crear una lista de materiales nos deberemos dirigir a la opción
|menu_bom_list|. Para ello, deberemos especificar su |bom_name|, que nos
servirá para identificarla. Ademas deberemos introducir sus |bom_inputs| y sus
|bom_outputs|, de la siguiente forma:

 * |bom_inputs|: Indicaremos la cantidad de cada producto que utilizaremos
   para realizar los productos resultantes. Siguiendo, el símil de la receta,
   se correspondería con los ingredientes y sus cantidades.
 * |bom_outputs|: Indicaderemos las cantidades de los productos resultantes.
   Cómo mínimo deberemos tener una linea con el producto final.


Por exemplo, si queremos definir la lista de materiales *Caja de 6 latas de
refresco*, crearíamos las siguiente lista de materiales:

+---------------------+-----------------------+
| |bom_inputs|        | |bom_outputs|         |
+=====================+=======================+
| 6 Latas refresco    | 1 Caja latas refresco |
+---------------------+-----------------------+
| 1 Caja              |                       |
+---------------------+-----------------------+
| 1 Plastico embalaje |                       |
+---------------------+-----------------------+

Listas de materiales de un producto
-----------------------------------

En el formulario de un producto podremos definir que listas de materiales se
pueden utilizar para producirlo.

.. note:: En la ficha de producto sólo podremos seleccionar aquellas listas
    de material que contengan el producto cómo alguna de sus salidas.

Utilizar listas de materiales en la orden de producción
-------------------------------------------------------

Si seleccionamos un |product| en la producción, podremos seleccionar una |bom|
relacionada con el mismo. Llegados a este punto, especificando la |quantity|
que queremos producir se nos rellenaran las |inputs| y las |outputs| con
los materiales necesarios para realizar la producción.

.. note:: En caso de que tengamos listas de materiales definidas en el
    producto el sistema nos cojera la primera por defecto.

.. |menu_bom_list| tryref:: production.menu_bom_list/complete_name
.. |quantity| field:: production/quantity
.. |product| field:: production/product
.. |bom| field:: production/bom
.. |bom_name| field:: production.bom/name
.. |bom_inputs| field:: production.bom/inputs
.. |bom_outputs| field:: production.bom/outputs


