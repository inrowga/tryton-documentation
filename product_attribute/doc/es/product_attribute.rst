Atributos del producto
======================

En los productos podrá añadir nuevos campos en ellos. Estos campos son agrupados
por grupos de atributo.

Cuando en el producto marque que grupo de atributos pertenece a ese producto,
dispondrá de los campos relacionados con este grupo y los podrá añadir en la
variante del producto los campos que desea. Por ejemplo:

* Grupo: Deportes
* Atributos: Tipología, Medio, Cardio, ...

.. inheritref:: product_attribute/product_attribute:section:atributos

Atributos
---------

Abra el menú |menu_attribute| y crea un nuevo atributo o campo. Para crear un nuevo
campo deberá rellenar:

* Nombre: Nombre interno del campo
* Etiqueta: El nombre visual
* Tipo:

  * Boleano
  * Entero
  * Fecha
  * Fecha/Hora
  * Numérico
  * Número coma flotante
  * Selección
  * Texto

Una vez diseñado los campos que desea que esten disponibles en los productos,
abra el menú |menu_attribute_set| para añadir grupos y a cada grupo que campos
van relacionados.

.. inheritref:: product_attribute/product_attribute:section:producto

Producto
--------

Abra el menú |menu_template| y crea un nuevo producto. Seleccione el grupo de
atributos que desea en el producto. Una vez seleccionado, en la variante del producto,
podrá añadir los campos extras del producto relacionado con el grupo de atributos.

.. |menu_attribute| tryref:: product_attribute.menu_attribute/complete_name
.. |menu_attribute_set| tryref:: product_attribute.menu_attribute_set/complete_name
.. |menu_template| tryref:: product.menu_template/complete_name
