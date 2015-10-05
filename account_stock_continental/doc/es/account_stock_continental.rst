
#:before:stock/stock:section:movimientos#

Contabilizar estocs
-------------------

Para poder mantener en la contabilidad el reflejo del valor de los estocs en 
tiempo real el usuario deberá: 

 1.- Habilitar la opción para poder realizar la contabilización de este en el 
     menú ejercicios fiscales, en la pestaña "Contabilización del stock", 
     seleccionando la opción *Continental*. 
 
 2.- Introducir en los productos, mejor en las categorías, las cuentas 
     contables que hace falta usar. En los apartados relacionados con el estoc.
     
 3.- Configurar la cuenta contable dónde se contabilizarán las actualizaciones 
     del precio de coste de la ficha del producto (si se quieren hacer).
     
A partir de estos pasos, por cada movimiento de estoc el programa hará un 
asiento de la siguiente forma:

 - Un apunte tendrá siempre la cuenta que hayamos introducido en el campo 
"Cuenta de estoc" de la categoría de producto (o del producto). Si es un 
movimiento de venta a esta cuenta irá en el haber porque resta valor a 
nuestro estoc. Si es uno de proveedor (compra) irá a la cuenta en el debe 
porque incrementa el valor del estoc. 
 
 - El otro apunte tendrá la cuenta contable de uno de los campos "Cuenta de 
estoc cliente", "Cuenta de estoc proveedor", "Cuenta de estoc producción", 
"Cuenta de estoc perdido/encontrado", según el tipo de movimiento de estoc que 
se esté haciendo en cada momento. 

Las cuentas contables a elegir las puede decir el usuario o consultar con su 
gestoria, pero si simplemente se quiere tener un reflejo detallado en una 
cuenta, podemos utilizar la 300000 como "Cuenta de estoc" y usar la 610000 o la 
710000 para proveedores, producción, clientes e inventario. Hay que tener en 
cuenta que el valor de perdido/encontrado no tener diferentes cuentas segon si 
son pérdidas o ganancias; aunque el valor final en la 300000 seguirá siendo 
correcto. 

**Diferentes cuentas para diferentes productos**

Podemos tener diferentes cuentas 300x para diferenciar el valor del estoc de 
los productos de cada categoría de manera que sea sencillo clasificar y 
control estas cantidades en el balance. 

.. note:: las cuentas que se quieran utilizar en los campos nombrados 
anteriormente deberán tener seleccionada la clase "Estoc".

.. important:: si se quiere utilizar una cuenta 610000, por ejemplo, 
recomendamos que se cree la cuenta 610001 para evitar problemas futuros con 
actualizaciones del plan contable.
