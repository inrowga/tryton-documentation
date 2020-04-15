=========
Productos
=========

El concepto *producto* en **Tryton** está compuesto de dos modelos: *la
plantilla de producto* (Producto) y *la variante del producto*
(producto). Esta separación se usa para poder definir un producto genérico
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


Crear un producto nuevo
=======================

El primer paso para crear un producto desde cero es crear una plantilla de
producto. Para ello accederemos al menú producto y ,clicando en *Nuevo*,
se nos abrirá el formulario de edición de la plantilla. En este formulario
deberemos especificar los campos nombre, tipo (indicando si se trata de un
*bien*, un *servicio* o un *activo*), el precio venta, el preciod e coste, el
método de coste (que veremos a continuación más detenidamente) y la
UdM por defecto (donde indicaremos la medida que utilizaremos para cuantificar el
producto). Además, si lo deseamos, le podemos indicar varias categorías para
agrupar el producto que estamos creando con otros de similar tipología.

.. view:: product.template_view_form
   :field: name

   Captura del menú productos

Si seleccionamos en el campo tipo la opción *Bienes*, nos aparecerá también
el campo consumible, que debemos marcar si queremos que no se controle el
número de existencias de nuestro producto. En caso de dejarlo sin marcar el
sistema llevará un control de la cantidad que tengamos de este producto.

En caso de que queramos que el producto este disponible para las compras,
debemos marcar el campo comprable. Una vez marcado nos aparecerá una nueva
pestaña **Proveedores**, dónde podremos definir la comprable, en caso de
que sea distinta de la UdM por defecto. Ademas podemos definir los
proveedores que nos subministran este producto, junto con el
nombre y el codigo propios del Proveedor.

Además, en el campo tiempo de espera se puede informar al sistema del tiempo de
entrega del producto por cada proveedor.

En caso de que queramos que el producto este disponible para las ventas,
debemos marcar el campo vendible. Una vez marcado nos aparecerá una nueva
pestaña **Clientes**, dónde podremos definir la UdM de venta (en caso de que sea
distinta de la UdM por defecto) y el tiempo de espera.

En la pestaña **Contabilidad** podremos especificar la configuración contable
del producto, pudiendo especificar los ingresos y los gastos.
Además podremos indicar también qué impuestos se aplicarán por defecto al
producto al venderlo, en el campo impuestos, y al comprarlo, en el campo
impuestos de proveedor. Por ejemplo, podríamos utilizar los siguientes valores para
estos campos:

* Ingresis: 700000 - Ventas de mercaderías en España.
* Gastos: 600000 - Compras de mercaderías.
* Impuestos clientes: IVA 21%
* Impuesto de proveedor : 21% IVA Soportado (operaciones corrientes)

Para simplificar la configuración contable de los productos, podemos marcar
los campos de la categoria contable y los impuestos para que se le aplique
al producto los igresoss|, los gastos, los impuestos de cliente y
los impuestos de proveedor definidos en la categoria del producto que hayamos
seleccionado en la pestaña anterior. En :ref:`cat-productos` podemos ver
como configurar la contabilidad de las categorías.

Para indicar que un producto determinado debe tener asignado obligatoriamente
un lote, debemos ir a la pestaña  **Lotes** y seleccionar los tipos de
ubicaciones en que queremos que este lote sea obligatorio.

.. figure:: images/required-lot.png

Esto hará que cuando se procese un movimiento de existencias de este producto
sea obligatorio un lote especificar un lote si el producto se esta recibiendo
o enviando desde una ubicación de los tipos seleccionados. Por ejemplo, en la
imagen anterior, el lote será obligatorio cuando hagamos una recepción de
proveedor, una devolución al mismo, un envío a cliente o una devolución de
cliente, ya que todos estos movimientos pasan por una ubicación de tipo
Proveedor o Cliente. Además, el lote no será obligatorio para los movimientos
internos en nuestro almacén, ya que no hemos marcado ni Almacenamiento ni
Producción, ni tampoco para los Inventarios, ya que tampoco hemos marcado
la opción Perdido/Encontrado.

Cálculo del precio de coste
---------------------------

En el campo metodo de coste indicaremos como se va a calcular el
precio de coste de cada producto. Podemos elegir entre varios posibles métodos:

* **FIFO**: Con esta opción, el precio de coste se actualiza de la misma forma
  que con la opción de Método de coste Promedio cuando el producto se compra o
  produce. Lo que aporta esta opción es que, cuando se mueven cantidades de
  este producto fuera de nuestro almacén (las enviamos a un cliente, a la
  ubicación de Perdido/encontrado al hacer un inventario o las usamos en una
  producción), el precio de coste del producto también se actualiza restándole,
  de forma ponderada, el coste de la cantidad enviada. Para calcular el coste
  de estas unidades se asume que el primero que entra es el primero que sale
  (FIFO en sus siglas en inglés) para ir a buscar el precio de compra de las
  primeras unidades que aún no se han gastado.

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

Crear variantes
---------------

Al crear la plantilla se nos generará por defecto una variante a la que le
podremos especificar su codigo y descripión. Dándole al botón *Nuevo* del
campo productos podremos crear tantas variantes como necesitemos e introducir
un codigo y una descripción  para cada una de ellas.

Otra opción para crear variantes es acceder por medio de la ruta producto y,
tras clicar en *Nuevo*, elegir la plantilla sobre la que queremos generar la
variante e indicar también, si queremos, su descripción y su código.

.. view:: product.product_view_form

   Captura de la vista formulario del producto

.. hint:: Dependiendo del momento en el que vayamos a crear la variante nos
   puede interesar más una opción que la otra: Si vamos a crear todas las
   variantes en el mismo momento en el que creamos la plantilla, nos resultará
   más cómodo crearlas desde la pantalla de edición de la plantilla. Por contra,
   si tan solo queremos añadir una variante más a una plantilla creada con
   anterioridad nos resultará más practico crear la variante desde
   producto.

Historial de costes del producto
--------------------------------

En la o las variantes del producto, a las que podemos acceder des de productos 
disponemos de un nuevo elemento relacionado a los resultados de la búsqueda: 
Historial de costes.

Al seleccionar esta opción, dispondremos de una nueva ventana con todo el historial
de la variante (producto), con las fechas y el precio de coste en cada fecha, si 
hay más de una. Así mismo el sistema, al canviar la vista del historial de costes 
nos mostrará un gráfico del historial de estos costes. 

.. |menu_product| tryref:: product.menu_product/complete_name

.. _product-para-amortizacion-de-activos:

Crear un producto para la amortización de activos
=================================================

Para poder contabilizar activos y su amortización es necesario definir productos de
tipo "Activo", por lo que tendremos que crear un nuevo producto indicándole que es
tipo *Activo* y en la pestaña *Contabilidad* marcar la casilla amortizable.
Además, también deberemos indicar las siguiente cuentas contables,
de las cuales las dos primeras son obligatorias:

* Compte:  Es la cuenta que será utilizada por la factura de proveedor
  para anotar la compra del activo. *Como por ejemplo la cuenta 213000 -
  Maquinaria.*

* Amortizable: Es la cuenta donde se anota la depreciación del activo
  en el haber, y el gasto en el debe de la cuenta de gastos. *Como por ejemplo la
  cuenta 281300 - Amortización acumulada de maquinaria*.

* Ingressos del compte: Se utilizará para reflejar los posibles ingresos generados
  por la venta del activo (en función de la depreciación ya realizada y el precio de
  venta).
  *Como por ejemplo la cuenta 771000 - Beneficios procedentes del inmovilizado
  material*.

* Perdidas:  Se utilizará para reflejar las posibles pérdidas generados por
  la venta del activo (en función de la depreciación ya realizada y el precio de
  venta). *Como por ejemplo la cuenta 681000 - Amortización del inmovilizado
  material.*


Si sabemos el número de meses en que se consideran cómo amortizados los
activos, lo podemos indicar en el campo durada de la amortizacion.

El producto sirve solamente de plantilla y para que el sistema pueda obtener en qué
cuentas contables debe realizar los apuntes. No es necesario, por tanto, crear un
nuevo producto para  cada ítem que queramos amortizar, solamente lo tendremos que
hacer si queremos cambiar alguna de las cuentas que intervienen en la compra,
amortización o venta.

Por ejemplo, podemos tener un sólo producto *Vehículo* y disponer de varios
vehículos a amortizar en la empresa, siempre y cuando deseemos que todos utilicen
la misma cuenta de activo, de amortización, de gastos y de ingresos (en caso que
lo vendamos).

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

* Ingresos
* Gastos
* Precio de venta
* Precio de coste
* Método de coste


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
a categorías y al clicar en el icono *Nuevo* se nos abrirá la
vista de edición de las categorías. En este formulario deberemos rellenar el
campo nombre con el nombre que le daremos y, si esta va a pertenecer a su
vez a otra categoría, lo indicaremos también en el campo padre. En
cambio, si son otras categorías las que dependerán de esta lo tendremos que
reflejar en el campo hijos de la pestaña **Hijos**. De esta manera,
podremos agrupar los productos en categorías y a su vez agrupar las categorías
en más categorías.


.. view:: product.category_view_form

  Captura de pantalla del formulario de la categoria del producto

Desde la pestaña **contabilidad** podremos indicar la cuenta de ingresos y
la cuenta de gasto, así como los impuestos de proveedor y los
impuestode clientes por defecto que se utilizarán en la categoria. De esta
forma, cuando configuremos un producto podremos indicarle que utilice las
cuentas e impuestos por defecto de la categoría a la que pertenece, y
simplificar así nuestra tarea. En caso de que en el producto se indiquen unas
cuentas o unos impuestos distintos a los de la categoría a la que pertenece,
los indicados en la categoría del producto no tendrán efecto.


Unidades de medida
==================
Podemos configurar las unidades de medida que utilizaremos para gestionar
nuestros productos accediendo a unidad y haciendo doble clic en la unidades
que queramos modificar o clicando en el botón *Nuevo* para crear una nueva
unidad. Los campos que deberemos rellenar son:

.. view:: product.uom_view_form

   Captura de pantalla del formulario de las unidades de medida del producto

* Nombre: Nombre que recibe la unidad.
* Símbolo: Símbolo que se utiliza para designar a la unidad.
* Categoía: Agrupa las distintas unidades por tipologías, podemos
  gestionar las categorías de las unidades de medida desde unidades de medida.
* factor y converción: Estos campos definen en las unidades de medida
  la relación existente entre una unidad y la considerada *base* o *estándar*.
  Por ejemplo si trabajamos con unidades de longitud, aunque tomemos como
  unidad de medida el metro, también podemos utilizar múltiplos y submúltiplos
  de dicha unidad cuando no sea cómodo trabajar en metros. Se definen de esta
  forma los decámetros, hectómetros o kilómetros como múltiplos del metro, o
  los decímetros, centímetros o milímetros como sus submúltiplos. El campo
  factor define la relación que guarda estos múltiplos o  submúltiplos
  con su unidad fundamental y el campo converción la relación inversa. De esta
  forma, el centímetro tendría un factor de 0,01 y una converción de 100,
  o el kilómetro tendría un factor de 1000, y un converción de 0,001. En
  caso del metro, así como de todas las unidades base, el valor de ambos campos
  será 1.
* Precisión de redondeo:Aquí indicaremos qué tipo de redondeo y que precisión queremos
  que se lleve a cabo con la Unidad de medida. Por ejemplo, podemos indica que
  se redondee el segundo decimal de uno en uno (introduciendo un valor de
  0,01), o que se redondee el tercer decimal de 5 en 5 (modificando el valor a
  0,005 e indicando en decimales a mostrar un valor de 3).
* Activable: Permite desactivar el registro sin borrarlo para aquellas
  unidades con las que no vayamos a trabajar.

