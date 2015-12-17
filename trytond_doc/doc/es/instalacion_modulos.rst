======================
Instalación de Módulos
======================

Tryton dispone de una gran cantidad de módulos que añaden diferentes 
funcionalidades al programa. En el siguiente enlace podréis encontrar el 
listado de módulos disponibles así como una pequeña descripción de las 
características que añaden al programa: http://apps.tryton-erp.es/

Para instalar cualquier módulo debemos acceder a la aplicación o bien con
el usuario y contraseña de Administrador o disponer de permisos para realizar 
esta acción en nuestro usuario. 

En el menú de la aplicación |menu_modulos| encontraremos
el listado de módulos disponibles, información sobre la versión, si se 
encuentran o no instalados y dos botones:

* Para actualizar (en los módulos ya instalados)

* Marca para instalar


.. view:: ir.module_view_tree

  Captura de pantalla de la lista de módulos


Con un doble clic sobre cualquier módulo accederemos a información sobre los 
módulos de los que depende y si éstos se encuentran ya instalados en el sistema.
Por ejemplo el módulo *account* depende de los módulos *company*, *currency*, *ir*, 
*party* y *res*.

.. view:: ir.module_view_form

   Captura de pantalla de un módulo en vista formulario

Desde las dos pantallas dispondremos del botón *Marca para instalar*. Esta acción 
no instala directamente el módulo sino que lo prepara para ser instalado junto 
con los módulos dependientes que no estén ya instalados en el programa. De este
modo podemos programar la instalación de varios módulos a la vez e incluso 
cancelar la instalación con el nuevo botón que nos aparecerá con el texto 
Cancelar la instalación

Para ejecutar la instalación de los módulos seleccionados debemos hacer clic
sobre el botón ejecutar acción y selecionar *instalaciones/actualizaciones
pendientes* (esta opción también está disponible en el menú principal en 
|menu_ejecutar|). Tras ello se nos mostrará una pantalla con todos los módulos 
a instalar que deberemos confirmar con el botón Inicia actualización. 

La duración del proceso dependerá de la cantidad y la tipología de los módulos 
y puede alargarse varias horas. Finalizada la instalación, el sistema nos 
informará que los módulos han sido instalados correctamente.

Pese a que el sistema actualiza de forma automática el menú principal, es 
aconsejable salir y volver a entrar a la aplicación antes de empezar a trabajar
con las nuevas funcionalidades.


.. |menu_modulos| tryref:: ir.menu_module_form/complete_name
.. |menu_ejecutar| tryref:: ir.menu_module_install_upgrade/complete_name