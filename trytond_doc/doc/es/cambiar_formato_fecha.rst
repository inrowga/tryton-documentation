======================================
Cambiar el formato de fechas y números
======================================

Tryton permite que el formato de la fecha que se muestra en la mayoría de 
documentos y el formato de los números (si hay o no separador de miles y el 
símbolo utilizado como separador de decimales) dependa del idioma con el que 
nos comunicamos con los terceros.

De esta forma es posible definir que un cliente con el que nos comunicamos
en inglés tenga el formato de fecha mes/día/año, mientras que con los clientes
que hablan francés el formato sea día/mes/año.

Para cambiar estos parámetros por idioma debemos dirigirnos a |menu_lang|.
Ahí nos aparecerá la lista de idiomas disponibles y podremos entrar en la ficha
del idioma del cual queremos cambiar el formato.

.. view:: ir.lang_view_form

   Captura pantalla del menu Idioma


El formato de fecha
===================

En el campo |date| podemos elegir el tipo de formato con el que se nos mostrarán
la fechas para el idioma en concreto. El tipo de formato se tiene que indicar
por medio de:

* **%d** para el día.

* **%m** para el mes.

* **%Y** para el año en cuatro dígitos.

* **%y** para el año en dos dígitos.

* Además, debemos indicar el tipo de separador que queremos utilizar entre los dígitos,
  siendo  ``%m/%d/%Y``, ``%m.%d.%Y`` y ``%m-%d-%Y``, los que se suelen utilizar.
  

.. note:: Aunque es poco habitual, se pueden utilizar otros símbolos para indicar
   el formato de la fecha. Podemos encontrar un listado más extendido
   `aquí <https://docs.python.org/2/library/datetime.html#strftime-and-strptime-behavior/>`_.
 
   
El formato de número
====================

Por otro lado, también es posible definir como se visualizarán e interpretaran 
los números por medio de los siguientes campos:

* |grouping|: indicamos cada cuantos dígitos queremos que se muestre el 
  separador de **miles**. Vea algunos ejemplos:
  
  * [3, 3, 0] El primer bloque (empezando por la derecha) utilizará 3 dígitos, 
    el siguiente bloque también 3 dígitos y los siguientes también utilizarán 3 
    (el cero indica continuidad). Por ejemplo: 1.234.567.890,00

  * [3, 2, 0] El primer bloque utilizará tres dígitos, el todos los siguientes 
    dos (porqué de nuevo el cero indica continuidad). Por ejemplo:
    1.23.45.67.890,00

  * [3, 2, 4] El primer bloque utilizará tres dígitos, el siguiente dos, el 
    siguiente cuatro y el resto no mostrarán separador de miles. Por ejemplo: 
    123456.7891.23.456,00

* |thousands_sep|: indicamos el símbolo que queremos utilizar como separador.
  En los ejemplos anteriores hemos utilizado el punto, pero se puede utilizar 
  cualquier otro o simplemente dejar el campo sin rellenar para que no se 
  utilice ningún símbolo, de tal manera que *mil* se expresaría: 1 000 
  
* |decimal_point|: es equivalente al campo anterior sólo que el símbolo
  indicado es el que se utilizará para indicar la separación de los decimales, 
  en este caso no es posible dejar el campo en blanco.

.. warning:: Es importante tener en cuenta que estas indicaciones también afectan
   a como reconoce el programa los valores que añade el usuario.
   Concretamente si utilizamos “,” como separador decimal y “.” como separador de
   miles, según la configuración de nuestro sistema operativo 
   no será posible o práctico utilizar el teclado numérico si éste utiliza el 
   punto en lugar de la coma.
   
.. hint:: Puede ser una buena solución no utilizar ningún
   separador de miles y poner la coma como separador de decimales. En este 
   caso todos los sistemas suelen interpretar tanto la coma como el punto 
   como separador decimal.
     
.. |menu_lang| tryref:: ir.menu_lang_form/complete_name
.. |date| field:: ir.lang/date
.. |grouping| field:: ir.lang/grouping
.. |thousands_sep| field:: ir.lang/thousands_sep
.. |decimal_point| field:: ir.lang/decimal_point