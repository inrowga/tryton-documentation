==========
Escritorio
==========

**Tryton** nos permite crear una pestaña que funcione como escritotio donde 
podremos elegir qué queremos que aparezca en él y adaptar estas seccione a
nuestras nedesidades y a nuestros intereses. Esta funcionalidad es habitual 
en entornos que el usuario del ERP recibe constantemente notificaciones y debe
controlar diferentes áreas de la gestión empresarial. 

Primero de todo tenemos que definir qué acciones serán las que queramos que 
nos aparezcan en el escritorio. Para saber cómo, podemos acceder a: 
:ref:`nueva-accion`  
       
       
Configuración
=============

Una vez tengamos creadas las acciones que queremos que nos aparezcan en el
escritorio tenemos que asociarlas a él. De todas las acciones, solo podremos 
seleccionar aquellas que están indicadas como |uso| dashboard. Para ello 
accederemos  al menú |menu_user| y nos iremos a la pestaña *Escritorio*. Desde
allí podremos indicar qué |dash_act| queremos que nos aparezcan en el Escritorio
y también la |dash_lay| que queramos que nos presente el escritorio.

.. view:: res.user_view_form
   :field:: dashboard_actions

.. Note:: El sistema solo permite tener un escritorio por usuario, por lo que no es
   posible tener varios con diferentes acciones.

.. |act_window| model:: ir.action.act_window
.. |keyword| model:: ir.action.keyword
.. |usage| field:: ir.action.act_window/usage
.. |menu_user| tryref:: res.menu_user_form/complete_name
.. |dash_act| field:: res.user/dashboard_actions
.. |dash_lay| field:: res.user/dashboard_layout