=========
Productos
=========

El concepto de producto en **Tryton** está compuesto de dos modelos: *la plantilla
de producto* (|menu_template|) y *la variante del producto* (|prod_menu|).
Esta separación se usa para poder definir un producto genérico (plantilla)
y las diferentes tipologías que pudieran haber de este producto (variante).
Podemos tener tantas variantes de una plantilla como queramos y cada
plantilla tendrá como mínimo una variante. Esto se debe a que en nuestra gestión,
los procesos (venta, producción, compra, amortización, etc), los haremos siempre
sobre la variante, nunca sobre la plantilla, por lo que cada plantilla necesita
como mínimo una variante.

Poniendo como ejemplo la venta de camisetas, la plantilla del producto podría ser
"Camiseta marca X" y una de las variantes "Camiseta marca X talla L color Rojo".
Tendremos tantas variantes como combinaciones de talla y colores, pero solo tendremos
una plantilla para este producto: "Camiseta marca X". En caso de solo tener
un color y una talla para este tipo de camiseta, tendríamos la misma plantilla, pero
solo una variante.


.. inheritref:: product/product:section:crear-un-producto

Crear un producto nuevo
=======================

Como ya hemos comentado, el primer paso para crear un producto es crear una
plantilla, esto lo haremos desde la ruta |menu_template| y clicando en *Nuevo*.
Una vez abierta la vista de edición de la plantilla, especificaremos cómo mínimo
su |name|, |type|, el |list_price|, el |cost_price|, el |cost_price_method| y su
|default_uom|. Además podremos especificarle una |category| para, posteriormente,
poder consultar todos los productos por categorías accediendo a
|menu_product_categories|.

.. view:: product.template_view_form
   :field: name

.. inheritref:: product/product:paragraph:compra-venta

Si seleccionamos el |type| *Bienes*, nos aparecerá el campo |consumable|, que
debemos marcar si queremos que no se controlen el número de existencias de
nuestro producto.

.. inheritref:: product/product:section:pestañas

Cálculo el precio de coste
--------------------------

El campo |cost_price_method| determina cómo se calcula el |cost_price|  de
cada producto. Los posibles métodos son:


.. inheritref:: product/product:bullet_list:cost_price_method_options

* **Fijo**
* **Promedio**


Método de coste Fijo
~~~~~~~~~~~~~~~~~~~~

Se establece el valor manualmente en la ficha de producto y éste no se
actualiza automáticamente bajo ninguna circunstancia.


Método de coste Promedio
~~~~~~~~~~~~~~~~~~~~~~~~

Cuando se realiza un albarán de proveedor (o una devolución a proveedor) se
recalcula el precio de coste del producto de forma ponderada; sumando (o
restando) el precio al que se ha comprado teniendo en cuenta la cantidad que
se está moviendo respecto al stock total de este producto en nuestro almacén
(Precio Medio Ponderado - PMP). Cuando se realiza una producción también se
recalcula el precio de coste de los productos producidos sumando, de forma
ponderada, el coste unitario de la producción.

.. Note:: Aunque se elija esta opción aún se podrá establecer el precio de coste de
   forma manual. Si hacemos esto estaremos indicando al sistema que las unidades
   de este producto que hay en nuestro almacén tienen el precio de coste unitario
   que indicamos y la próxima vez que se recalcule se tomará de base este precio
   de coste.


.. inheritref:: product/product:section:crear-variantes

Crear variantes
---------------

Al crear la plantilla se nos generará por defecto una variante y podremos especificar
su |code| y su |description|. Dándole al botón *Nuevo* del campo |products|
podremos crear tantas variantes como necesitemos e introducir un |code| y una
|description| para cada una de ellas.

Otra opción para crear variantes es acceder por medio de la ruta |prod_menu| y, tras
clicar en *Nuevo*, elegir la |template| sobre la que queremos generar la variante e
indicar también, si queremos, su |description| y su |code|.

.. hint:: Dependiendo de el momento en el que vayamos a crear la variante nos puede
   interesar más una opción que la otra: Si vamos a crear todas las variantes en
   el mismo momento en el que creamos la plantilla, nos resultará más como crearlas
   desde la pantalla de edición de la plantilla. Por contra, si tan solo queremos
   añadir una variante más a una plantilla creada con anterioridad nos resultará
   más practico crear la plantilla desde |prod_menu|.


Desactivar productos
====================

A veces necesitamos desactivar un producto porque ya no trabajamos con
él y no resulta práctico verlo siempre en los distintos listados de productos.
En **Tryton** no es posible eliminar ningún registro ya tenemos algún documento
(factura, albarán, presupuesto, etc) con el que está relacionado. Es por ello, que
la única opción para estos casos es dejar el producto inactivo, de esta forma no nos
aparecerá en el listado de productos, pero seguirá relacionado con los distintos
documentos. Para más información podemos acceder a :ref:`desactivar-registros`.


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


.. inheritref:: product/product:section:unidades_de_medida

Unidades de medida
==================

La unidad de medida está definida por los campos:

* |name_uom|: Nombre que recibe la unidad.
* |symbol_uom|: Símbolo que se utiliza para designar a la unidad.
* |category_uom|: Agrupa las distintas unidades por tipologías.
* |factor_uom| y |rate_uom|: Estos campos definen en las unidades de medida
  la relación existente entre una unidad de medida y la considerada *base*.
  Por ejemplo si tomamos como unidad de medida el metro, normalmente se utilizan
  también múltiplos y submúltiplos de dicha unidad cuando no es cómodo trabajar en
  metros. Se definen de esta forma los decámetros, hectómetros o kilómetros como
  múltiplos del metro, o los decímetros, centímetros o milímetros como sus
  submúltiplos. Pues bien, el campo |factor_uom| define la relación que guarda estos
  múltiplos/submúltiplos con su unidad fundamental y el campo |rate_uom| la relación
  inversa. De esta forma, el centímetro tendría un |factor_uom| de 0,01
  y una |rate_uom| de 100, o el kilómetro tendría un |factor_uom| de 1000, y un
  |rate_uom| de 0,001.
* |rounding_uom|:Aquí indicaremos qué tipo de redondeo y que precisión queremos
  que se lleve a cabo con la Unidad de medida. Por ejemplo, podemos indica que se
  redondee el segundo decimal de uno en uno (introduciendo un valor de 0,01), o que
  se redondee el tercer decimal de 5 en 5 (modificando el valor a 0.005 e indicando
  en |digits_uom| un valor de 3).
* |digits_uom|: El número de dígitos que queremos que se muestre con la medida.
* |active_uom|: Permite desactivar el registro sin borrarlo.

.. Nota:: Para los campos |rate_uom| y |rounding_uom|, en caso de tratarse de la
   unidad base, el valor indicado en estos campos debe de ser 1.


.. |menu_template| tryref:: product.menu_template/complete_name
.. |name| field:: product.template/name
.. |menu_product_categories| tryref:: product.menu_category_tree/complete_name
.. |type| field:: product.template/type
.. |consumable| field:: product.template/consumable
.. |category| field:: product.template/category
.. |list_price| field:: product.template/list_price
.. |cost_price| field:: product.template/cost_price
.. |cost_price_method| field:: product.template/cost_price_method
.. |default_uom| field:: product.template/default_uom
.. |active| field:: product.template/active
.. |products| field:: product.template/products
.. |code| field:: product.product/code
.. |description| field:: product.product/description
.. |prod_menu| tryref:: product.menu_product/complete_name
.. |template| field:: product.product/template
.. |name_uom| field:: product.uom/name
.. |symbol_uom| field:: product.uom/symbol
.. |category_uom| field:: product.uom/category
.. |factor_uom| field:: product.uom/factor
.. |rate_uom| field:: product.uom/rate
.. |rounding_uom| field:: product.uom/rounding
.. |digits_uom| field:: product.uom/digits
.. |active_uom| field:: product.uom/active