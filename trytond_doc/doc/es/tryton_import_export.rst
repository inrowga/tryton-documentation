=======================
Importar/Exportar datos
=======================

Existen diferentes formas de exportar datos de nuestro ERP hacia otra aplicación.

Tryton ofrece un sistema por defecto básico de Importación/Exportación para
cualquier registro/modelo de nuestro ERP. Se usa ficheros CSV para la importación/exportación.
Estos ficheros lo podrá abrir con cualquier herramienta de hoja de cálculo, como el
LibreOffice.

En todos los ejemplos para la importación/exportación de registros, nos situaremos
en el lugar donde queremos hacer la acción. Por ejemplo, si deseamos exportar productos,
iremos al listado productos. En el caso de importar terceros, deberemos abrir el listado de terceros

.. inheritref:: trytond_doc/tryton_import_export:title:exportar_datos

Exportar datos
==============

Una vez situados en el listado que deseamos exportar, usaremos el buscador para filrar
los registros que deseamos exportar.

Para exportar a CSV el icono de herramientas disponemos de la opción: **Exportar datos**.

La pantalla de exportación nos creará un fichero CSV que lo podemos abrir con
cualquier aplicación de hoja de cálculo (por ejemplo LibreOffice).

Disponemos de 3 columnas:

* Todos los campos: Los campos disponibles a exportar.
* Acciones: Acciones a realizar para exportar.
* Campos a exportar: Los campos que exportaremos.

Seleccionaremos los campos de la columna de la izquierda (todos los campos) y con
la opción de **Añadir** se activaran en la columna de la derecha (campos a exportar).

También disponemos de más acciones:

* Eliminar. Elimina un campo de la columna *Campos a exportar*.
* Limpiar. Elimina todos los campos de la columna *Campos a exportar*.
* Guardar exportación. Permite guardar como favorito esta acción.
* Eliminar exportación. Permite un favorito ser eliminado.

En las **opciones** nos permite si el fichero CSV se abrirá con nuestro editor
favorito de CSV o guardar en el disco. En el caso de abrir un CSV, se abrirá
con la aplicación que tenga asignado con los ficheros CSV.

.. image:: images/tryton-export_csv.png

.. inheritref:: trytond_doc/tryton_import_export:title:importar_datos

Importar datos
==============

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

.. image:: images/tryton-import_csv.png

.. note:: Para importar datos, deberán añadir todos los campos que sean requeridos.
            Consulte con su técnico que campos son requeridos.

.. note:: El sistema de importación sólo crea nuevos registros; no modifica.
            Consulte con su técnico otras herramientas de importación.

.. note:: El sistema de importación NO permite campos relacionados. Por ejemplo,
            no podrá importar direcciones ya las direcciones van relacionadas con
            un tercero. Consulte con su técnico otras herramientas de importación.

.. warning:: El campo ID en la importación de datos no se debe usar. Si ha seleccionado
             este campo en la exportación de datos, deberá eliminarlo o no seleccionar
             en la lista de campos a importar.
