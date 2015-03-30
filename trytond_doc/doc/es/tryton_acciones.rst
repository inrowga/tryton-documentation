==================
Acciones en Tryton
==================

Una *acción* en Tryton es un asistente que realizará cálculos para generar unos
valores nuevos o nuevos registros. Generalmente una acción abre una ventana
flotante, que contendrá un formulario, para completar y procesar dicha
información.

--------------------
Desde la vista lista
--------------------

Para ejecutar una acción desde la vista de lista hay que:

 * Seleccionar los registros de la lista sobre los que queremos ejecutar la
   acción. Para ello es suficiente hacer clic con el ratón en el primero de los
   registros, pulsar la tecla **Mayúsculas** y sin soltarla, marcar el último
   de los registros que deseamos incluir en la selección. Si los registros no
   están consecutivos, si no que deseamos seleccionar registros "salteados", en
   lugar de pulsar la tecla **Mayúsculas**, pulsaremos la tecla *Control* e
   iremos marcando uno por uno los registros que queramos incluir en la
   selección.

 * Hacer clic en sobre icono **Ejecutar acción** y seleccionar la acción que se
   desee ejecutar.

-------------------------
Desde la vista formulario
-------------------------

Desde la vista de formulario, sólo se puede ejecutar acciones para el registro
que esté abierto en ese momento, y el procedimiento es el mismo que desde la
vista de lista.

.. figure:: images/tryton-action.png

   Acción desde un pedido de venta para el envío de correo electrónico en Tryton

.. _nueva-accion:

-------------------------
Crear acciones de ventana
-------------------------

Por medio del menú |menu_ventana| acceredemos a un listado de todas las
acciones de ventana predeterminadas. Desde aquí podremos crear nuevas acciones
o duplicar las predeterminadas para poder modificarlas a nuestro gusto.

.. warning:: No es recomendable modificar ninguna |act_window| de las
   predeterminadas ya que estas son compartidas por todos los usuarios y puede
   provocar errores en la gestión realizada por estos.

Para crear una nueva acción clicaremos en el botón *Nuevo* y se nos abrirá la
Vista formulario que deberemos rellenar según la tipología de la acción que
queramos crear. Los campos a rellenar son:

* |model|: Aquí indicaremo sobre qué modelo vamo a realizar la |act_window|.

* |usage|: Este campo lo dejaremos en blanco a no ser que la |act_window| esté
  destinada a ser una sección del Escritorio, en tal caso deberemos de indicar
  que el |usage| será *dashboard* (todo en minúsculas). De esta manera,
  podremos seleccionar la |act_window| desde la configuración del Escritorio.

* |views|: Las acciones de ventana pueden tener diferentes vistas (arbol,
  formulario, calendraio, gráfico...). En caso de que la |act_window| esté
  destinada al *Escritorio* solo se utilizará la primera de la lista.

* |act_domains|: no afectan al escritorio, pero definen en qué estado pueden
  estar los modelos.

* |domain|: mostrará la informaicón que deseemos, podemos seleccionar qué
  estado de modelo queremos visualizar. No podremos modificarlo desde el
  escritorio.

  .. code::

     Registros en estado borrador: [('state', '=', 'draft')]

     Registro en estado borrador o finalizado [('state', 'in', ('draft', 'done'))]

* |context|: el tipo de información que se muestra, habitualemten vendrá
  predefinido por la acción de ventana.

* |order|: como se ordena la información a mostrar.

 .. code::

     Fecha de creación ascendente:  [('create_date', 'ASC')]

* |search|: filtro que se aplica por defecto i que despues se puede modificar
  desde la barra de búsqueda de la pestaña.

  .. code::

     Tercero que contenga la letra "j" [('party', 'ilike', '%j%')]

* |limit|: nombre de registro máximos que se mostrarán.

En la pestana *Acciones de teclado* indicaremos la ruta de acceso que queremos
que tenga la nueva acción. En caso de que la nueva Acción de ventana esté
destinada al escritorio, deberemos dejar el campo en blanco.

.. Note:: En caso de realizar un duplicado de alguna |act_window| tenemos que
          acordarnos de eliminar las |keywords| desde la pestaña
          correspondiente de la copia para que esta no tenga la misma ruta de
          acceso de menú que la original.

También podremos elegir que grupo de usuarios tendrán acceso a esta acción de
ventana desde la pestaá *Grupos*.

Creación de filtros y dominios
------------------------------
Para crear nuevos filtros o dominios seguiremos el orden ``[('nombre.campo',
'relación', 'condición')]``.

* *Nombre.campo*: incidaremos aquí sobre qué campo queremos que se realice
  la búsqueda.

* *Relación*: La relación que se ha de cumplir entre el nombre.campo y la
  condición.  Algunos ejemplos:

  .. code::

     '=', '<', '<=', 'like' (como =), 'ilike' (para que no distinga
     entre mayúsculas y minúsculas)

* *Condición*: Aquello que se ha de cumplir un registro para que aparezca
  en la búsqueda. Algunos signos útiles:

  .. code::

    '¡condición' (diferente a 'condición'), %condición% (cualquier
    resultado antes y depues de 'condición'


.. |menu_ventana| tryref:: ir.menu_action_act_window/complete_name
.. |act_window| model:: ir.action.act_window
.. |keywords| field:: ir.action.act_window/keywords
.. |model| field:: ir.action.act_window/res_model
.. |usage| field:: ir.action.act_window/usage
.. |views| field:: ir.action.act_window/act_window_views
.. |act_domains| field:: ir.action.act_window/act_window_domains
.. |domain| field:: ir.action.act_window/domain
.. |context| field:: ir.action.act_window/context
.. |order| field:: ir.action.act_window/order
.. |search| field:: ir.action.act_window/search_value
.. |limit| field:: ir.action.act_window/limit