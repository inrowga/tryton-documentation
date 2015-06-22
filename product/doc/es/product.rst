=========
Productos
=========

El concepto *producto* en **Tryton** está compuesto de dos modelos: *la
plantilla de producto* (|menu_template|) y *la variante del producto*
(|menu_prod|). Esta separación se usa para poder definir un producto genérico
(plantilla) y las diferentes tipologías que pudieran haber de este producto
(variante). Podemos tener tantas variantes de una plantilla como queramos y
cada plantilla tendrá como mínimo una variante. Esto se debe a que, en nuestra
gestión, los procesos (venta, producción, compra, amortización, etc.) los
realizaremos siempre sobre la variante, nunca sobre la plantilla, por lo que
cada plantilla necesitará como mínimo una variante.

Poniendo como ejemplo la venta de camisetas, la plantilla del producto podría
ser "Camiseta marca X" y una de sus variantes "Camiseta marca X talla L".
Tendremos tantas variantes como tallas tengamos, pero solo una plantilla para
este producto: "Camiseta marca X". En caso de que solo tengamos una talla para
este tipo de camiseta, tendríamos la misma plantilla, pero solo una variante.


.. inheritref:: product/product:section:crear-un-producto

Crear un producto nuevo
=======================

El primer paso para crear un producto desde cero es crear una plantilla de
producto. Para ello accederemos al menú |menu_template| y ,clicando en *Nuevo*,
se nos abrirá el formulario de edición de la plantilla. En este formulario
deberemos especificar los campos |name|, |type| (indicando si se trata de un
*bien*, un *servicio* o un *activo*), el |list_price|, el |cost_price|, el
|cost_price_method| (que veremos a continuación más detenidamente) y la
|default_uom| (donde indicaremos la medida que utilizaremos para cuantificar el
producto). Además, si lo deseamos, le podemos indicar una |category| para
agrupar el producto que estamos creando con otros de similar tipología.

.. view:: product.template_view_form
   :field: name
   
   Captura del menú productos 

.. inheritref:: product/product:paragraph:compra-venta

Si seleccionamos en el campo |type| la opción *Bienes*, nos aparecerá también
el campo |consumable|, que debemos marcar si queremos que no se controle el
número de existencias de nuestro producto. En caso de dejarlo sin marcar el
sistema llevará un control de la cantidad que tengamos de este producto.

.. inheritref:: product/product:section:pestanas

Cálculo del precio de coste
---------------------------

En el campo |cost_price_method| indicaremos como se va a calcular el
|cost_price| de cada producto. Podemos elegir entre varios posibles métodos:

.. inheritref:: product/product:bullet_list:cost_price_method_options

* **Fijo**: Se establece el valor manualmente en la ficha de producto y éste no
  se actualiza automáticamente bajo ninguna circunstancia.

* **Promedio**: Cuando se realiza un albarán de proveedor (o una devolución al
  proveedor) se recalcula el precio de coste del producto de forma ponderada;
  sumando (o restando) el precio al que se ha comprado teniendo en cuenta la
  cantidad que se está moviendo respecto al stock total de este producto en
  nuestro almacén (Precio Medio Ponderado - PMP). Cuando se realiza una
  producción también se recalcula el precio de coste de los productos
  producidos sumando, de forma ponderada, el coste unitario de la producción.

.. Note:: Aunque se elija la opción **Promedio** aún se podrá establecer el
   precio de coste de forma manual. Si hacemos esto estaremos indicando al
   sistema que las unidades de este producto que hay en nuestro almacén tienen
   el precio de coste unitario que indicamos y la próxima vez que se recalcule
   se tomará de base este precio de coste.

.. inheritref:: product/product:section:crear-variantes

Crear variantes
---------------

Al crear la plantilla se nos generará por defecto una variante a la que le
podremos especificar su |code| y |description|. Dándole al botón *Nuevo* del
campo |products| podremos crear tantas variantes como necesitemos e introducir
un |code| y una |description| para cada una de ellas.

Otra opción para crear variantes es acceder por medio de la ruta |menu_prod| y,
tras clicar en *Nuevo*, elegir la |template| sobre la que queremos generar la
variante e indicar también, si queremos, su |description| y su |code|.

.. view:: product.product_view_form

.. hint:: Dependiendo del momento en el que vayamos a crear la variante nos
   puede interesar más una opción que la otra: Si vamos a crear todas las
   variantes en el mismo momento en el que creamos la plantilla, nos resultará
   más cómodo crearlas desde la pantalla de edición de la plantilla. Por contra,
   si tan solo queremos añadir una variante más a una plantilla creada con
   anterioridad nos resultará más practico crear la variante desde
   |menu_prod|.

.. inheritref:: product/product:section:relacionado_con_los_productos   

Trabajar con productos en multicompañía
---------------------------------------

Si trabajamos en multicompañía, todos los productos que tengamos en la base de
datos se compartirán entre nuestras empresas. Esto significa que si creamos un
producto con la Empresa *A*, también lo veremos disponible en la empresa *B*. A
pesar que los productos que veamos sean los mismos, no todos los datos de un
determinado producto serán los mismos en cada una de nuestras compañías.

Por ejemplo, podemos entrar en la compañía *A* y definir un precio de venta
para un producto y después entrar en la compañía *B* y definir otro precio
de venta para el mismo producto. Cada empresa trabajará con el precio de venta
que le haya indicado al sistema.

A continuación detallamos los campos que no son comunes entre las distintas
empresas que podamos tener:

.. inheritref:: product/product:bullet_list:multicompany_fields

* |list_price|
* |cost_price|
* |cost_price_method|


Desactivar productos
--------------------

A veces necesitamos desactivar un producto porque ya no trabajamos con
él y no resulta práctico verlo siempre en los distintos listados de productos.
En **Tryton** no es posible eliminar ningún registro si ya tenemos algún
documento (factura, albarán, presupuesto, etc.) con el que está relacionado. Es
por ello, que la única opción para estos casos es dejar el producto inactivo,
de esta forma no nos aparecerá en el listado de productos, pero seguirá
relacionado con los distintos documentos. Para más información podemos acceder
a :ref:`desactivar-registros`.


.. _cat-productos:

Crear categorías de productos
=============================

**Tryton** nos permite agrupar los productos según nuestras necesidades
o intereses por medio de las categorías. Para crear una nueva deberemos acceder
a |menu_product_categories| y al clicar en el icono *Nuevo* se nos abrirá la
vista de edición de las categorías. En este formulario deberemos rellenar el
campo |cat_name| con el nombre que le daremos y, si esta va a pertenecer a su
vez a otra categoría, lo indicaremos también en el campo |cat_parent|. En
cambio, si son otras categorías las que dependerán de esta lo tendremos que
reflejar en el campo |cat_childs| de la pestaña **Hijos**. De esta manera,
podremos agrupar los productos en categorías y a su vez agrupar las categorías
en más categorías.


.. view:: product.category_view_form


.. inheritref:: product/product:section:unidades_de_medida

Unidades de medida
==================
Podemos configurar las unidades de medida que utilizaremos para gestionar
nuestros productos accediendo a |menu_uom| y haciendo doble clic en la unidades
que queramos modificar o clicando en el botón *Nuevo* para crear una nueva
unidad. Los campos que deberemos rellenar son:

.. view:: product.uom_view_form

* |name_uom|: Nombre que recibe la unidad.
* |symbol_uom|: Símbolo que se utiliza para designar a la unidad.
* |category_uom|: Agrupa las distintas unidades por tipologías, podemos
  gestionar las categorías de las unidades de medida desde |menu_cat_uom|.
* |factor_uom| y |rate_uom|: Estos campos definen en las unidades de medida
  la relación existente entre una unidad y la considerada *base* o *estándar*.
  Por ejemplo si trabajamos con unidades de longitud, aunque tomemos como
  unidad de medida el metro, también podemos utilizar múltiplos y submúltiplos
  de dicha unidad cuando no sea cómodo trabajar en metros. Se definen de esta
  forma los decámetros, hectómetros o kilómetros como múltiplos del metro, o
  los decímetros, centímetros o milímetros como sus submúltiplos. El campo
  |factor_uom| define la relación que guarda estos múltiplos o  submúltiplos
  con su unidad fundamental y el campo |rate_uom| la relación inversa. De esta
  forma, el centímetro tendría un |factor_uom| de 0,01 y una |rate_uom| de 100,
  o el kilómetro tendría un |factor_uom| de 1000, y un |rate_uom| de 0,001. En
  caso del metro, así como de todas las unidades base, el valor de ambos campos
  será 1.
* |rounding_uom|:Aquí indicaremos qué tipo de redondeo y que precisión queremos
  que se lleve a cabo con la Unidad de medida. Por ejemplo, podemos indica que
  se redondee el segundo decimal de uno en uno (introduciendo un valor de
  0,01), o que se redondee el tercer decimal de 5 en 5 (modificando el valor a
  0,005 e indicando en |digits_uom| un valor de 3).
* |active_uom|: Permite desactivar el registro sin borrarlo para aquellas
  unidades con las que no vayamos a trabajar. 

.. |menu_template| tryref:: product.menu_template/complete_name
.. |menu_prod| tryref:: product.menu_product/complete_name
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
.. |template| field:: product.product/template
.. |cat_name| field:: product.category/name
.. |cat_parent| field:: product.category/parent
.. |cat_childs| field:: product.category/childs
.. |menu_uom| tryref:: product.menu_uom_form/complete_name
.. |name_uom| field:: product.uom/name
.. |symbol_uom| field:: product.uom/symbol
.. |category_uom| field:: product.uom/category
.. |menu_cat_uom| tryref:: product.menu_uom_category_form/complete_name
.. |factor_uom| field:: product.uom/factor
.. |rate_uom| field:: product.uom/rate
.. |rounding_uom| field:: product.uom/rounding
.. |digits_uom| field:: product.uom/digits
.. |active_uom| field:: product.uom/active