=================
Usuarios / Grupos
=================

Una empresa tiene diferentes trabajadores, pero no todos los trabajadores
disponen de acceso a nuestro ERP y los que disponen de acceso no tiene 
porque tener los mismos permisos. Por tanto, sólo deberemos dar de alta 
usuarios que dispondrá acceso a nuestro ERP.

.. inheritref:: trytond_doc/admin_usuarios_grupos:section:usuarios

Usuarios
========

Accederemos por medio de la ruta menu usuario y se nos abrirá una nueva pestaña
con el listado de todos los usuarios que tenemos creados. Podemos modificar cualquiera 
seleccionándolo o crear uno nuevo clicando en el botón *Nuevo*.

Dentro de la ficha del usuario, podremos modificar el nombre, de
usuario o nick, la contraseña, el correo  o indicar un idioma para la interfaz.

En la pestaña *Acciones* se podrá predeterminar qué pestañas se abrirán al iniciarse
el programa. Para ello clicaremos en el signo "**+** y seleccionaremos aquellas 
pestañas que queremos que se nos abran.

En la pestaña *Permisos de acceso* podremos indicar a qué grupos va a pertenecer el 
usuario.

Cada usuario, por su parte puede editar su firma, idioma, contraseña mediante el 
menú principal *Usuarios* de la barra de herramientas.

.. warning:: Cuando realizamos modificaciones en algún usuario, para que estas
   se hagan efectivas, el usuario modificado debe de desconectarse y volver a
   entrar en el sistema.

.. hint:: Por regla general, no es recomendable borrar registros (entre ellos 
   los usuarios) en Tryton, Si tenemos un trabajador dado de baja o vacante, 
   lo más recomendable es *deseleccionar* el campo activo  para que se desactive
   su acceso del sistema.

Grupos
======

Accederemos por medio de Grupos.

Cuando hayamos accedido al menú, nos aparecerá un listado con todos los grupos
creados. A medida que se vayan instalando los diferentes módulos, se irán añadiendo
grupos por defecto. Estos grupos darán acceso a ciertos objetos, algunos con 
permisos totales, otros solo de lectura, etc.

Si accedemos a la vista detallada de cualquier grupo, en primera instancia nos
mostrará un listado con todos los usuarios que son miembros del grupo [#f1]_, si 
hacemos doble clic sobre cualquier usuario se nos abrirá una ventana flotante con
los mismos campos que en el menú *Usuarios*.

Para realizar cambios en los permisos accederemos a la pestaña *Permisos de acceso*
donde podremos concretar qué tipo de permiso tendrá el grupo en cuestión.

.. hint:: No es aconsejable modificar los permisos de los grupos predefinidos,
   si queremos restringir el acceso de algún grupo en concreto o hacer que unos
   usuarios tengan un acceso completo a algún módulo y otros lo tengan más restringido,
   lo aconsejable es duplicar el grupo en cuestión, dejar el original tal cual está y
   restringir el acceso del nuevo grupo.

En la pestaña *Permisos de acceso* podremos diferenciar entro los siguientes cuatro
campos:


.. view:: res.group_view_form
   :field: model_access

   Campos de la pestaña *Permisos de acceso*


* Acceso a menús: Aquí seleccionaremos a qué modelos de los diferentes módulos
  se podrá acceder desde el grupo en cuestión. Una vez seleccionado el modelo, podemos
  elegir entre si el grupo tendrá permiso para leer, modificar, crear, y/o eliminar.

* Accesi a campos: Aquí seleccionaremos los campos concretos sobre los que queremos
  modificar los permisos, pudiendo elegir también entre leer, modificar, crear y/o
  eliminar. En caso de que queramos que un determinado grupo tenga acceso a un módulos 
  (por ejemplo módulo ventas) pero no queremos que puedan ver un campo en concreto
  (por ejemplo precio de coste) deberemos seleccionar aquí el campo en cuestión y
  dejar sin seleccionar ninguno de los permisos (Leer, modificar, crear y eliminar).
  
* Acceso a menús Desde aquí podremos seleccionar o modificar las rutas de acceso
  que queremos que tenga el grupo (por ejemplo, podemos hacer que el grupo *Contabilidad*
  tenga también acceso al menú *banca*.
  
* Reglas: En este campo podemos concretar qué acciones puede hacer el grupo con
  los accesos del menú (por ejemplo si queremos que un grupo tenga acceso al menú
  ventas, pero que únicamente pueda ver los registro de ventas y no crearlos,
  eliminarlos o modificarlos. 

.. rubric:: Notas a pie de página
.. [#f1] Un usuario puede pertenecer a tantos grupos como se desee, cada grupo da
   acceso a un módulo, por lo que a cuantos más grupos pertenezca más permisos
   tendrá el usuario.

