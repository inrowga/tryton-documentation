=====
Lotes
=====

El módulo **Lotes** define lotes de producto.

Un lote, por defecto, simplemente es un número para etiquetar movimientos.
Cuando es necesario seleccionar el tipo de ubicación involucrado en un
movimiento es posible definir lotes por producto.

-------------------
Creación de un lote
-------------------

Para añadir un nuevo lote a Tryton siga los siguientes pasos:

* Abra el menú |menu_lot_form|
* Haga clic en el botón nuevo lote
* Introduzca el número de lote y el producto

.. |menu_lot_form| tryref:: stock_lot.menu_lot_form/complete_name


------------------------
Añadir lote a movimiento
------------------------

Para añadir un lote a un movimiento de stock siga los siguientes pasos:

* Abra el menú **Logística** y el tipo de albarán correspondiente al que quiera
  añadir el lote (proveedor, cliente, interno).
* Busque y abra el albarán concreto a añadir el lote.
* Abra cada línea de albarán (movimiento), e introduzca el lote en el campo
  correspondiente.

En el caso de albaranes de cliente, en el momento de realizar el envío un albarán,
el lote que disponemos del movimiento interno será asignado al movimiento de salida.

-------------------
Asignación de lotes
-------------------

En caso de que tengamos instalado el módulo stock_lot, dispondremos del campo 
lote en los movimientos. 

Para añadir un lote a un movimiento de se debe:
Abra cada línea de albarán (movimiento)
Introduzca el lote en el campo correspondiente.
En caso de que el lote no exista, lo puede crear directamente desde el propio 
movimiento. 

En el momento de realizar el envío del albarán, el lote de los movimientos de 
inventario será asignado al movimiento de salida, por lo que no hará falta 
introducirlo dos veces. 

Autoasignación de lotes en albaranes de salida
----------------------------------------------

En los productos que el lote sea requerido para los movimientos de salida, se 
asignará un lote por defecto en el momento que el albarán pase por el estado 
“esperando”.
Para la asignación automática de lotes:
El producto debe disponer la opción de lote requerido (en qué ubicaciones el 
lote es requerido).
Debe haber cantidades disponibles de lote en el producto.

En el caso de solicitar más cantidades del producto que cantidades disponibles 
en el lote, en el momento de asignar un número de lote, se dividirán las líneas 
del albarán con cantidades según números de lotes disponibles.

----------------------
Escaneo de movimientos
----------------------

En caso de que tengamos instalado el módulo *stock_scanner* podremos escanear 
los movimientos pendientes de realizar, mostrándonos información sobre los 
movimientos pendientes, internos y de salida. 

.. Captura de pantalla que mostra aquest escaneig

En esta pantalla veremos los productos que están pendientes de coger para el 
albarán. Si añadimos un producto escaneado, el sistema nos propondrá una 
cantidad a escanear. Desde la configuración de stock (Logística -> 
Configuración 
-> Stock) podremos determinar el valor por defecto que nos propone el sistema 
en 
el campo cantidad. Si no tenemos marcada la opción *Rellenar cantidad* el 
sistema nos propondrá 1.0 por defecto, y si lo tenemos marcado el sistema nos 
propondrá la cantidad total pendiente de escanear. 

Una vez rellenado el producto y cantidad, nos aparecerá un botón para aceptar.
Así, pulsando en el botón *Aceptar*, a la cantidad pendiente de ese producto se 
le restarà el valor del campo cantidad y se limpiará el campo producto 
escaneado para que podamos realizar un nuevo escaneo. 

Cuando hayamos escaneado todas las cantidades pendientes de una línea, esta 
dejará de aparecer en el listado de movimientos pendientes. Así, cuando este 
listado esté vacío querrá decir que hemos escaneado todos los movimientos y 
podemos seguir con el flujo normal del albarán. 

Introducción de lotes
---------------------

En caso que queramos especificar el lote al que se corresponde ese escaneo, lo 
podemos introducir en el campo *Lote*. Este lote se asignará al movimiento 
escaneado. En caso de introducir diferentes lotes para el mismo producto, los 
movimientos serán divididos asignando un lote a cada uno de los movimientos.
