=======================
Importar/Exportar datos
=======================

Existen diferentes formas de exportar datos de nuestro ERP hacia otra aplicación.

Tryton ofrece, por defecto, un sistema básico de Importación / Exportación para
cualquier registro / modelo de nuestro ERP. Se usan ficheros CSV para la 
importación / exportación.
Estos ficheros los podras abrir con cualquier herramienta de hoja de cálculo, 
como el LibreOffice.

En todos los ejemplos para la importación / exportación de registros, nos 
situaremos en el lugar donde queremos hacer la acción. Por ejemplo, si deseamos 
exportar productos, iremos al listado productos. En el caso de importar 
terceros, deberemos abrir el listado de terceros.

--------------
Exportar datos
--------------


Para exportar a CSV en el icono de herramientas disponemos de la opción: 
**Exportar datos**.

El asistente de exportación nos creará, por defecto, un fichero CSV que lo 
podemos abrir con cualquier aplicación de hoja de cálculo (por ejemplo 
LibreOffice), aunque siempre podremos guardar el archivo con el formato que 
prefiramos.

Este asisten se divide en tres filas, la primera dónde veremos las 
*Exportacions predeterminadas*, una segunda fila dividida en tres columnas y 
una tercera línea de *Opciones*. Las tres columnas se dividen en:

* *Todos los campos*: Los campos disponibles a exportar.
* *Acciones*: Acciones a realizar para exportar.
* *Campos a exportar*: Los campos que exportaremos.

Seleccionaremos los campos de la columna de la izquierda (todos los campos) y con
la opción de *Añadir* se activarán en la columna de la derecha (campos a 
exportar).

También disponemos de más acciones:

* *Eliminar*. Elimina un campo de la columna *Campos a exportar*.
* *Limpiar*. Elimina todos los campos de la columna *Campos a exportar*.
* *Guardar exportación*. Permite guardar como favorito esta acción.
* *Eliminar exportación*. Permite un favorito ser eliminado.

En las *Opciones* nos permite escoger si el fichero CSV se abrirá con nuestro 
editor predeterminado de CSV o guardar el archivo en nuestro disco. En el caso 
de abrir un CSV, se abrirá con la aplicación predeterminada que tenga asignado 
a este tipo de ficheros.

Exportar más de 1000 registros
==============================

Por defecto tryton muestra siempre 1000 registros en pantalla. Si se quiere ir 
a los 1000 siguientes hay que hacer clic sobre las flechas verdes de la parte 
inferior derecha de la imagen para ir a la siguiente página:


Esto permite que la aplicación sea suficientemente ágil y no tenga que cargar 
decenas de miles de datos innecesariamente.

Hay que tener en cuenta que las exportaciones que realicemos se limitarán 
también a estos 1000 registros. Sin embargo, es posible cambiar este límite de 
registros para realizar una exportación extraordinaria en un momento 
determinado. 

Para ello, debemos dirigirnos al menú superior, a la parte izquierda “Opciones 
> Límite de búsqueda…” y cambiar el número de registros que queremos visualizar 
por cada página.

Abrir la exportación con Excel 2010
===================================

Si la exportación se debe abrir con office 2010 podemos encontrarnos que Office 
2010 no lo abra bien directamente. Tenemos dos posibilidades:

* Una vez se abre Excel automáticamente desde la exportación veremos que nos 
  sale el contenido en una sola columna. Debemos seleccionarla toda y nos 
  dirigimos al menú Datos / Texto en columnas. Nos aparecerá un asistente y 
  deberemos indicarle que el separador utilizado es la coma. No acostumbra a 
  ser problemático dejar el resto de separadores como válidos. La codificación
  / locale deberá ser “UTF-8”. Una vez finalizado el asistente ya nos saldrá 
  cada campo en una columna distinta.
  
* En lugar de abrir directamente, también podemos indicarle a Tryton que en 
  lugar de abrir queremos guardar. Si guardamos el fichero en formato texto y 
  lo abrimos posteriormente con Excel, veremos el mismo asistente indicado en 
  el punto anterior, completaremos los mismos campos, obteniendo de forma 
  directa cada campo en una columna distinta.
  
.. Note:: Al menos en Excel 2003 no es posible indicar la codificación del
  texto (en este caso, Unicode UTF-8) cuando Excel se abre automáticamente. En 
  este caso la única opción válida es la número 2. Es importante tenerlo en 
  cuenta porque no sólo puede afectar a la visualización de símbolos raros sino 
  que además puede que algunos datos (líneas enteras) no sean importados con 
  los graves problemas que esto significa. 

.. figure:: images/tryton-export_csv.png

   Exportación a CSV 


--------------
Importar datos
--------------

Muy similar con la acción *Exportar datos*. Esta acción importa **nuevos** registros
en el modelo que nos situamos para la importación.

Para la importación dispondremos de 3 columnas para:

* Todos los campos. Que campos disponibles tenemos.
* Acciones. Acciones a realizar para importar.
* Campos a importar. Los campos que importaremos del CSV.

Seleccionaremos los campos de la columna de la izquierda (todos los campos) y con
la opción de **Añadir** se activaran en la columna de la derecha (campos a importar).

También disponemos de más acciones:

* Eliminar. Elimina un campo de la columna *Campos a importar*.
* Limpiar. Elimina todos los campos de la columna *Campos a importar*.
* Auto-detectar. Revisa las cabeceras del CSV que concuerden con los campos del
  registro.

Para importar deberemos seleccionar el archivo de nuestro disco duro en *Archivos
a importar*, como si lo deseamos, podemos especificar los campos de nuestro CSV.

.. figure:: images/tryton-import_csv.png

   Importación desde CSV


.. note:: Para importar datos, deberán añadir todos los campos que sean requeridos.
            Consulte con su técnico que campos son requeridos.

.. note:: El sistema de importación sólo crea nuevos registros; no modifica.
            Consulte con su técnico otras herramientas de importación.

.. warning:: El campo ID en la importación de datos no se debe usar. Si ha seleccionado
             este campo en la exportación de datos, deberá eliminarlo o no seleccionar
             en la lista de campos a importar.

----------
Tutoriales
----------

* `Importación de terceros mediante CSV`_
* `Importación de productos mediante CSV`_

.. _`Importación de terceros mediante CSV`: http://www.tryton-erp.es/posts/importacion-de-terceros-mediante-csv.html
.. _`Importación de productos mediante CSV`: http://www.tryton-erp.es/posts/importacion-de-productos-mediante-csv.html

