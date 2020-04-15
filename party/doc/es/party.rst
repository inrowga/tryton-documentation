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


En la pestanya Logística podemos definir la ubicación del cliente y la
ubicación de proveedor que se utilizará por defecto para los albaranes
relacionados con este tercero.

Podremos introducir la información bancaria del tercero en el campo
cuentas bancarias.

Desde la pestaña relaciones podremos definir con que otros terceros está
relacionado este tercero. Esto es útil para indicar, por ejemplo los contactos
de una misma empresa, o incluso sus empleados. Para crear una relación basta
con indicar el tipo de relación y el tercero relacionado.

Crear un tercero
================

Para crear un tercero tendremos que acceder al menú tercero y clicar en el
botón *Nuevo*. En el formulario que se nos abrirá deberemos rellenar los
siguientes campos:


* Nombre: con el nombre del tercero.
* Idioma: donde indicaremos el idioma por defecto con el que nos dirigiremos al
  tercero en los documentos (facturas, albaranes, cartas, etc.) que le
  enviemos.
* Direccines: en este campo introduciremos las direcciones, tanto postales
  como de facturación, del tercero. Podremos indicar tantas direcciones como
  queramos, para introducir una nueva dirección clicaremos en el botón *Nuevo*
  a la derecha del campo y rellenaremos los campos internos con la información
  correspondiente.
* Métodos de contacto: aquí podremos indicar números de teléfono, direcciones
  de correo electrónico, direcciones web, etc. del tercero.
* Categorías: en este campo podremos añadir categorías previamente definidas
  o crear otras nuevas. Las categorías sirven para agrupar los terceros según
  la tipología de estos y poder clasificarlos más fácilmente. Posteriormente
  podremos acceder al menu categoríasy consultar los terceros de una o varias
  categorías.

.. warning:: Para eliminar una dirección o un medio de contacto, lo haremos
   con el :ref:`botón de eliminar de la dirección<tryton-campos-one2many>`. No
   usaremos el menú desplegable que aparece cuando hacemos clic sobre botón de
   herramientas superior, ya que en ese caso eliminaríamos el tercero.

.. note:: Para poder editar manualmente el código del tercero, sólo hay que
   quitar del apartado de **configuración** el campo *Secuencia del tercero*.
   Así cuando creemos el tercero nos dejará poner manualmente el código.

.. view:: party.party_view_form
   :field: name

   Vista formulario de un Tercero

A la pestaña **Identificadores** introduciremos los códigos del tercero
como CIF/NIF. En el caso de ser un CIF/NIF europeo, seleccionaremos la opción
"VAT" (y nos validará el número introducido).

Si accedemos a la pestaña **Contabilidad** podremos seguir introduciendo
información sobre nuestro cliente. Los campos que deberemos indicar en esta
pestaña son:

* A pagar y a cobrar: indicaremos las cuentas que se
  utilizarán cómo cuentas a cobrar/pagar por defecto en las facturas
  relacionadas con el tercero.
* Regla de impuesto de cliente y Regla de impuesto de proveedor:
  especificaremos la regla de impuestos que queremos que se aplique 
  al tercero. 


Encontrar terceros sin NIF
==========================

Si deseamos encontrar todos los terceros para los que no hayamos introducido un
NIF podemos hacerlo introduciendo el siguiente filtro en la pantalla de
terceros: **CIF/NIF: =""**. Es importante no olvidarse de las dos dobles
comillas al final que indican al programa que el campo debe estar vacío.


Categorías
==========

Como ya hemos visto anteriormente, por medio de las categorías podemos agrupar
terceros según los criterios que queramos, veremos la categoria en la parte
inferior derecha. Por medio de la opción de menú categorías podemos
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

* Ubicación de cliente
* Ubicación de proveedor
* Procedimiento de reclamación

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


Informes
========

Dispone de dos informes:

* El informe **Etiquetas** crea un documento con el nombre y direcciones de
  todos los terceros seleccionados. Este informe está generado para ser
  imprimido en etiquetas que se puedan pegar en un sobre.

* El informe **Carta** crea un documento editable con la cabecera de la
  compañía, la dirección del destinatario, la fecha, un saludo, un final y la
  firma del usuario que lanza el informe.


Tipos de relaciones
-------------------

En el menú tipo de relaciones podemos definir los tipos de relaciones entre
terceros.

Un tipo de relación, puede tener una relación inversa. Una relación inversa
nos define otra relación que se aplica para todos los terceros que tienen
una relación pero en sentido inverso. Por ejemplo, si definimos la relación
"tiene como empleado" cómo relación inversa de "es empleado de" y definimos
que el tercero A es empleado del tercero B, con la relación inversa
automáticamente obtendremos que el el tercero B tiene como empleado al tercero
A.

.. note:: Es importante rellenar ambos casos de la relación inversa. Siguiendo
    el ejemplo anterior deberemos definir cómo inversa de "tiene como empleado"
    la relación "es empleado de", y a la vez la relación "es empleado de" cómo
    inversa de "tiene como empleado". De este modo, se ligaran los dos lados
    de la relación.


Configuración
=============

En configuración podemos encontrar distintas opciones
que nos permitirán adaptar la gestión de los terceros a nuestras necesidades.

.. view:: party.party_configuration_view_form
   :field: party_lang

   Configuración de terceros


En la secuencia del tercero podremos indicar el tipo de secuencia que queremos que
sigan los terceros. Podemos elegir una de las creadas anteriormente o crear una
nueva desde aquí (para ver como configurar secuencias:
:ref:`admin-secuencias`). Para poder editar manualmente el código del tercero,
sólo hay que dejar en blanco el campo.

