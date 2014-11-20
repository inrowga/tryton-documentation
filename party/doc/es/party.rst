================================
Terceros (clientes, proveedores)
================================

**Tryton** dispone de un mecanismo muy potente para la gestión de terceros y 
contactos pero es necesario utilizarlo adecuadamente. un tercero será cualquier
persona física o jurídica con la que la empresa tenga algún tipo de relación
en algún momento. Así de genérico y así de amplio es el concepto. Por tanto,
serán terceros los clientes, los proveedores, los empleados así como otras
personas como, por ejemplo, clientes potenciales.

La ventaja de trabajar de esta forma en lugar de tener una ficha para el
proveedor y otra para el cliente es que permite tener una sola ficha cuando
la empresa o persona física es cliente y proveedor al mismo tiempo. También
puede ocurrir que un tercero sea cliente y empleado de la empresa al mismo
tiempo. Además, para poder organizar mejor nuestra cartera de terceros, 
podemos crear tantas catgegorias y subcategorias de terceros como queramos
para agruparlos dependiendo de los criterios que queramos.


.. inheritref:: party/party:section:crear-un-tercero

crear un tercero
================

Para crear un tercero simplemente debemos introducir un |name| para
identificarlo. Además puede ser interesante introducir un |lang|, para que
los documentos relacionados con el mismo (por ejemplo las facturas que les
podamos emitir) se generen en el idioma seleccionado. Para indicar su,
|vat_code|, debemos irnos a la pestaña *Contabilidad*, indicar el país en el
campo |vat_country| y el número en el campo |vat_number|.

.. view:: party.party_view_form
   :field: name

También podremos indicar las |addresses| de un tercero, y sus
|contact_mechanisms|.

.. warning:: Para eliminar una dirección o un medio de contacto, lo haremos
   con el :ref:`botón de eliminar de la dirección<tryton-campos-one2many>`. No
   usaremos el menú desplegable que aparece cuando hacemos clic sobre botón de
   herramientas superior, ya que en ese caso eliminaríamos el tercero.

Tryton nos permite clasificar los terceros por categorías, por lo que podremos
establecer tantas categorías como queramos para cada tercero dependiendo de 
la tipología de este. Podemos separarlos entre *clientes*, *proveedores*, 
*colaboradores*, *empleados*, etc. Posteriormente podremos acceder a la ruta
|menu_party_categories| para consultar todos los terceros de una categoría. 
Para ello, simplemente hace falta hacer doble clic sobre la categoría y se nos 
abrirá el listado de todos los terceros de la misma.


Categorias
==========

Por medio de las categorías podemos agrupar terceros según los criterios que 
queramos. Las categorías las podemos indicar en la parte inferior derecha de 
la ficha de terceros. Desde este campo podemos añadir categorias previamente 
definidas o crear otras nuevas (un tercero podrá pertenecer a más de una
categoría). De esta forma podremos clasificar los terceros fácilmente.
Además, un tercero puede pertenecer a más de una categoría.

  ..Contest::
    Captura de pantalla
    

Por medio de la opción de menú |menu_category| podemos acceder a todas las 
categorías que hemos creado y haciendo doble clic sobre cualquiera de ellas
se nos abrirá una nueva pestaña con todos los terceros pertenecientes a la 
categoría seleccionada. Volviendo a la pestaña anterior, también es posible
crear nuevas categorías y subcategorías para gestionar mejor nuestra cartera
de terceros.

  ..Contest::
    Captura de pantalla
    
.. |menu_category| tryref:: party.menu_category_tree/complete_name


Desactivar terceros
===================

A veces es necesario poder desactivar un tercero porque ya no trabajamos con
el mismo, pero esto no es posible porque ya tenemos algún documento (factura,
presupuesto, etc) que hace referencia al mismo.

En este caso podremos desactivarlo tal como se explica en
:ref:`desactivar-registros`.


.. inheritref:: party/party:section:terceros-multicompania

Trabajar con terceros en multicompañía
======================================

Por defecto, todos los terceros se comparten entre la compañías. Esto significa
que si creamos un tercero en la empresa A, también lo tendremos disponible en
la empresa B. Además podemos utilizarlo sin problemas indistintamente en una
compañía o en la otra. Lógicamente, los documentos (ventas, compras, albaranes,
facturas, etc.) no se van a compartir y sólo los podremos ver en la misma
compañía en las que han sido creados.

A pesar que los terceros sean los mismos en todas la compañías esto no significa
que  todos los datos de un determinado tercero sean los mismos en todas las
compañías.

A continuación detallamos los campos que dependen de la compañía en terceros:



.. inheritref:: party/party:section:informes



Informes
========

Dispone de dos informes:

* El informe **Etiquetas** crea un documento con el nombre y direcciones de 
  todos los terceros seleccionados. Este informe está generado para ser
  imprimido en etiquetas que se puedan pegar en un sobre.

* El informe **Carta** crea un documento editable con la cabecera de la
  compañía, la dirección del destinatario, la fecha, un saludo, un final y la
  firma del usuario que lanza el informe.

.. inheritref:: party/party:section:configuration

Configuración
=============

En |menu_party_configuration| podemos encontrar distintas opciones
que nos permitirán adaptar la gestión de los terceros a nuestras necesidades.

.. view:: party.party_configuration_view_form
   :field: party_lang

En |party_sequence| podremos indicar el tipo de secuencia que queremos que sigan
los terceros. Podemos elegir una de las creadas anteriormente o crear una
nueva desde aquí. (para ver como configurar secuencias: :ref:`admin-secuencias`)
Para poder editar manualmente el código del tercero, sólo hay que dejar
en blanco el campo.

En el campo |party_lang| podemos especificar el idioma que se utilizará por
defecto para la creación de nuevos terceros. Esto solo aplicará para los nuevos
terceros creados a partir de este momento, y siempre podremos modificar
manualmente el idioma en caso de que este deba ser distinto del idioma por
defecto.


.. |name| field:: party.party/name
.. |lang| field:: party.party/lang
.. |vat_code| field:: party.party/vat_code
.. |vat_country| field:: party.party/vat_country
.. |vat_number| field:: party.party/vat_number
.. |addresses| field:: party.party/addresses
.. |contact_mechanisms| field:: party.party/contact_mechanisms
.. |categories| field:: party.party/categories
.. |menu_party_categories| tryref:: party.menu_category_tree/complete_name
.. |party_sequence| field:: party.configuration/party_sequence
.. |party_lang| field:: party.configuration/party_lang
.. |menu_party_configuration| tryref:: party.menu_party_configuration/complete_name

