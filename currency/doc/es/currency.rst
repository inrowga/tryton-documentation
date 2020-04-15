
.. _gestion-moneda:

======
Moneda
======

Accederemos al menú por medio de moneda.

Una vez abierta la pestaña, dentro nos encontraremos ante un listado con todas las monedas con las
que podemos trabajar. Podemos realizar búsquedas por medio del filtro para poder localizar cualquier
divisa y acceder a la vista de edición de cada moneda haciendo doble clic sobre la que nos interesa
o seleccionándola y clicando luego en el botón *Cambiar de vista*.

Una vez dentro podremos modificar los distintos campos, así como la tasa de cambio y el formato de
cada moneda.

.. Note::
   Podemos indicar si la moneda está activa para nuestras gestiones, si la dejamos inactiva no
   nos aparecerá en la vista anterior pero la podremos encontrar utilizando la barra de búsqueda y
   buscando por el campo activo y poniendo *Falso* como condición.


Tasas de cambio
===============

En la pestaña *Tasa de cambio* podremos reflejar los valores del cambio y sus variaciones a lo largo
del tiempo. Para ello debemos clicar en el botón *Nuevo* dentro de tarifa y nos aparecerá
una ventana flotante donde podremos introducir la fecha del cambio y la tasa de cambio.
Para calcular la tasa de cambio actual, el programa siempre utilizará la tasa de cambio cuya fecha
sea más próxima a la actual, de tal forma que si la tasa de cambio del dolar respecto al euro el
01.09.2014 estaba en *1,3128* e introducimos esta información, el sistema realizará la  conversión
para todas las facturas a partir del 01.09.2014 con dicha tasa de cambio. Si el 01.10.2014
introducimos la tasa a *1,2624*, a partir de esa fecha se calculará la conversión con la nueva tasa
de cambio. De esta forma queda reflejado en el sistema un histórico de tasas y en caso de calcular
una factura de fecha anterior a la última  modificación, el sistema utilizará la tasa de cambio del
histórico informada para la fecha de la factura.

.. Note::
   Como moneda de referencia se toma el Euro, todas las monedas por defecto aparecen con
   una tasa de cambio 0 excepto el Euro, cuya tasa de cambio es de 1.

Formato de la divisa
====================

En esta pestaña podemos modificar varios campos relativos al formato que presentará la moneda
en el programa.

* Decimales: Podemos decidir los decimales que se mostrarán cuando trabajemos con la moneda.
#Modificar a ir.lang
* Agrupación: Podemos indicar como agrupar los dígitos de la moneda.

* Separador de miles: Signo que separará el dígito de las centenas del de los millares. En caso
  de dejar el campo en blanco los dos dígitos estarán separado por un espacio (1 000, con espacio,
  1.000 si introducimos un ".", 1,000 si introducimos una “,”, etc.).

* Separador de decimales: A diferencia de campo anterior, este no lo podemos dejar en blanco y
  debemos elegir qué signo utilizaremos para la separación de decimales, siendo en Europa más habitual
  utilizar la *coma* para ello.

* Signo positivo: Si utilizamos algún signo para informar que la cantidad es positiva
  (por defecto este campo está en blanco).

* Signo negativo: Si utilizamos algún signo para indicar que la cantidad es negativa
  (por defecto este campo está rellenado con el signo "-").

* El signo positivo va delante: Indicar, en caso de haber signo positivo, si se expresará al
  inicio de la cifra o no.
  
* El signo negativo va delante: Indicar si el signo negativo se expresará delante de la cifra.

* Signo positivo separado por espacio: Si este signo irá separado del número por un  espacio o inmediatamente antes.

* Signo negativo separado por espacio: Si este signo irá separado del número por un  espacio o inmediatamente antes.

.. Note::
   Si en separador de miles dejamos el campo vacío, a la hora de introducir números por medio del teclado
   numérico, los puntos los reconocerá como comas, en caso contrario cuando introduzcamos el punto entenderá
   que estamos introduciendo un millar.

