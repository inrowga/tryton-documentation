================================
Terceros (clientes, proveedores)
================================

**Tryton** dispone de un mecanismo muy potente para la gestión de terceros y
contactos pero es necesario utilizarlo adecuadamente. Un tercero será cualquier
persona física o jurídica con la que la empresa tenga algún tipo de relación
en algún momento. Así de genérico y así de amplio es el concepto, por tanto,
serán terceros los clientes, los proveedores, los empleados así como otras
personas como, por ejemplo, clientes potenciales.

La ventaja de trabajar de esta forma, en lugar de tener una ficha para el
proveedor y otra para el cliente, es que permite tener una sola ficha cuando
la empresa o persona física es cliente y proveedor al mismo tiempo. También
puede ocurrir que un tercero sea cliente y empleado de la empresa al mismo
tiempo. Además, para poder organizar mejor nuestra cartera de terceros,
podemos crear tantas categorías y subcategorías de terceros como queramos
para agruparlos según nuestros criterios.


.. inheritref:: party/party:section:crear-un-tercero

Crear un tercero
================

Para crear un tercero tendremos que acceder al menú |menu_party| y clicar en el
botón *Nuevo*. En el formulario que se nos abrirá deberemos rellenar los
siguientes campos:

.. inheritref:: party/party:bullet_list:campos_general

* |name|: con el nombre del tercero.
* |lang|: donde indicaremos el idioma por defecto con el que nos dirigiremos al
  tercero en los documentos (facturas, albaranes, cartas, etc.) que le
  enviemos.
* |addresses|: en este campo introduciremos las direcciones, tanto postales
  como de facturación, del tercero. Podremos indicar tantas direcciones como
  queramos, para introducir una nueva dirección clicaremos en el botón *Nuevo*
  a la derecha del campo y rellenaremos los campos internos con la información
  correspondiente.
* |contact_mechanisms|: aquí podremos indicar números de teléfono, direcciones
  de correo electrónico, direcciones web, etc. del tercero.
* |categories|: en este campo podremos añadir categorías previamente definidas
  o crear otras nuevas. Las |categories| sirven para agrupar los terceros según
  la tipología de estos y poder clasificarlos más fácilmente. Posteriormente
  podremos acceder a |menu_categories| y consultar los terceros de una o varias
  categorías.

.. warning:: Para eliminar una dirección o un medio de contacto, lo haremos
   con el :ref:`botón de eliminar de la dirección<tryton-campos-one2many>`. No
   usaremos el menú desplegable que aparece cuando hacemos clic sobre botón de
   herramientas superior, ya que en ese caso eliminaríamos el tercero.
   

.. view:: party.party_view_form
   :field: name
   
   Vista formulario de un Tercero


Si accedemos a la pestaña **Contabilidad** podremos seguir introduciendo
información sobre nuestro cliente. Los campos que deberemos indicar en esta
pestaña son:

.. inheritref:: party/party:bullet_list:campos_contabilidad

* |vat_number|:  donde indicaremos el número fiscal del tercero.
* |vat_country|: en el que indicaremos el país de procedencia del tercero.


Categorías
==========

Como ya hemos visto anteriormente, por medio de las categorías podemos agrupar
terceros según los criterios que queramos, veremos la categoria en la parte 
inferior derecha. Por medio de la opción de menú |menu_categories| podemos 
acceder a todas las categorías que hemos creado y haciendo doble clic sobre 
cualquiera de ellas se nos abrirá una nueva pestaña con todos los terceros 
pertenecientes a la categoría seleccionada. Volviendo a la pestaña anterior, 
también es posible crear nuevas categorías y subcategorías para gestionar mejor 
nuestra cartera de terceros.


.. view:: party.category_view_form

   Vista de categorias


Desactivar terceros
===================

A veces es necesario poder desactivar un tercero porque ya no trabajamos con
el mismo, pero el sistema no nos dejará eliminarlo si ya tenemos algún
documento (factura, presupuesto, etc) que hace referencia al mismo. En este
caso podremos desactivarlo tal y como se explica en
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
compañías. Y lo mismo ocurre para el producto.

Por ejemplo, las cuentas contables asociadas al producto son únicas por 
compañía. Podemos entrar en la compañía A y definir la cuenta de gastos del 
producto a la 60000001 y después entrar en la compañía B y ahí definir la cuenta 
de gastos del mismo producto como 60000002.

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
   
   Configuración de terceros


En |party_sequence| podremos indicar el tipo de secuencia que queremos que
sigan los terceros. Podemos elegir una de las creadas anteriormente o crear una
nueva desde aquí (para ver como configurar secuencias:
:ref:`admin-secuencias`). Para poder editar manualmente el código del tercero,
sólo hay que dejar en blanco el campo.

En el campo |party_lang| podemos especificar el idioma que se utilizará por
defecto para la creación de nuevos terceros. Esto solo aplicará para los nuevos
terceros creados a partir de este momento, y siempre podremos modificar
manualmente el idioma en caso de que este deba ser distinto del idioma por
defecto.

.. |menu_party| tryref:: party.menu_party_form/complete_name
.. |name| field:: party.party/name
.. |lang| field:: party.party/lang
.. |vat_code| field:: party.party/vat_code
.. |vat_country| field:: party.party/vat_country
.. |vat_number| field:: party.party/vat_number
.. |addresses| field:: party.party/addresses
.. |contact_mechanisms| field:: party.party/contact_mechanisms
.. |categories| field:: party.party/categories
.. |menu_categories| tryref:: party.menu_category_tree/complete_name
.. |party_sequence| field:: party.configuration/party_sequence
.. |party_lang| field:: party.configuration/party_lang
.. |menu_party_configuration| tryref:: party.menu_party_configuration/complete_name