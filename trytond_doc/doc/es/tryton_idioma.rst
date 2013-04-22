======
Idioma
======

El cliente GTK Tryton permite instalar tantos idiomas como se necesiten.

-----------------------------
Instalación de nuevos idiomas
-----------------------------

Es tan sencillo como ir al menú **Administración/Localización/Idiomas** e ir marcando
los casilleros seleccionables de la columna *Traducible* de los idiomas deseados.
Esto instalará el/los idioma(s) en su sistema.

---------------------------------------
Cambio de idioma del cliente GTK Tryton
---------------------------------------

Cada usuario puede acceder al servido Tryton en el idioma que desee. Para ello sólo
tiene que abrir el menú **Usuario/ Preferencias** y en la pestaña **Preferencias**
seleccionar el idioma que desee.

------------------
Campos traducibles
------------------

Los campos traducibles disponen de una "banderita" para indicar que ese
`campo es traducible`_.

.. _campo es traducible: tryton_campos.html#traduccion

-----------------------------
Comunicación con los clientes
-----------------------------

En la ficha de cada cliente (tercero) puede especificar que idioma usa el mismo
para comunicarse con él. De esta forma, se puede configurar una plantillas de correo,
por ejemplo, para que los comunicados que se envíen a un cliente cuyo idioma es el
inglés, se le envíen los correos electrónicos en inglés, pese a que el usuario
del servidor Tryton utilice el castellano.

.. note:: El tiempo de instalación de cada idioma viene determinado por el número
          total de módulos que se tengan instalado: a más módulos instalados,
          más tiempo tarda la instalación de cada idioma.

---------------------
Activación de idiomas
---------------------

La gestión de los idiomas en Tryton los encontrará en **Administrador/Localización/Idiomas**

En Tryton puedemos activar los idiomas según:

 * **Traducible**: Los idiomas que estará disponible en nuestro ERP tanto la
   interficie gráfica (idioma de los usuarios) como la traducción de los campos
   multilingue.
 * **Activo**: Los idiomas que estará disponible en nuestras empresas
   (idioma de la empresa)

.. warning:: La traducción de los módulos se encuentran dentro del código del
             módulo y sólo se carga el idioma cuando este es traducible. Por tanto,
             si activa un idioma como traducible, deberá actualizar su Tryton server
             con la opción **-u all** para que se actualizen los idiomas y los nuevos,
             se carguen.
