---------------
Conexión Tryton
---------------

Tryton es una aplicación ERP cliente-servidor.

Necesitaremos

* **Tryton Client** Aplicación de escritorio que se instala en las máquinas
  locales.
* **Tryton Server** Servidor de Tryton que se instala en servidores (técnico).

Para el uso de Tryton necesitamos:

* Conectividad a internet o a la red
* Acceso al servidor Tryton Server
* Trabajar con una base de datos

Clientes
========

Para conectarse a Tryton debemos utilizar el cliente GTK. La descarga se puede
realizar desde `descarga de Tryton`_

.. _descarga de Tryton: http://www.tryton.org/es/downloads.html

.. warning:: Consulte con su técnico que versión de Tryton debe usar. Debe usar
             la misma versión que la del servidor de Tryton. No podrá conectar
             si las versiones entre cliente y servidor no coinciden. 

Conexión
========

El cliente GTK de Tryton tiene por defecto un selector de perfiles en el que se
pueden configurar distintos datos de conexión a diferentes servidores. Para acceder
a él, hay que hacer clic sobre el botón "Administra Perfiles" de la ventana de login:

.. figure:: images/tryton-login.png

   Ventana de login del cliente Tryton

Para crear un perfil de conexión al servidor de Tryton, hay que hacer clic en el
botón Añade de la parte inferior izquierda y rellenar los siguientes datos:

* **Dirección IP o dominio del servidor**
* **Puerto** Por defecto 8000
* **Base de datos**: Seleccionar una del menú desplegable.
* **Usuario**

.. figure:: images/tryton-profile.png

   Perfiles del cliente Tryton

Una vez rellenados dichos datos, hay que hacer clic en el botón Aceptar y una vez
de nuevo en la ventana de login, sólo hay que seleccionar el perfil correspondiente
e introducir la contraseña para conectarse.

Selección base de datos
=======================

Cuando nos conectamos al servidor, podemos escoger la base de datos sobre la que
queremos trabajar. Esta selección se realiza desde la ventana de Administración
de perfiles.

Si deseamos trabajar con varias bases de datos, podemos abrir varios clientes de
Tryton para conectarnos a cada una de las bases de datos.

Crea base de datos
==================

Tryton nos permite crear fácilmente nuevas bases sin información ni módulo 
alguno instalado pero con acceso a todos los módulos disponibles.  

Para crear una base de datos en Tryton debemos acceder al menú general de la 
aplicación (esquina superior izquierda) en Fichero > Base de datos > Nueva base 
datos

Tras seleccionar la opción, aparecerá una pantalla donde nos solicitará la 
siguiente información:

 * Contraseña del servidor Tryton (deberemos disponer de dicha contraseña para 
   poder instalar la nueva base de datos en el servidor)
 
 * Nombre de la nueva base de datos
 
 * El idioma inicial de la base de datos
 
 * La contraseña y la confirmación de la contraseña para el administrador 
   (deberá ser la misma pero más adelante puede modificarse)

Presionando el botón *Crear* iniciaremos el proceso de creación de una nueva 
base de datos vacía y sin módulos dónde podremos empezar a trabajar.

Ventana flotante pidiendo la contraseña
=======================================

Si el usuario esta inactivo cierto tiempo (por ejemplo, esta en una reunión o ha
salido de su espacio de trabajo) y se ha dejado el cliente GTK abierto, le pedirá
de nuevo la contraseña para entrar de nuevo sin cerrar el cliente.

Por defecto son 600 segundos de inactividad hasta que le pide de nuevo una contraseña.
Contacte con nuestros técnicos si desean un tiempo mayor de inactividad.

Modificar la contraseña del usuario
===================================

La seguridad de Tryton obliga a la identificación mediante usuario y contraseña 
para acceder a la aplicación así como tras un periodo de inactividad. Dicha 
contraseña puede modificarse en cualquier momento por el usuario.

Para modificar la contraseña deberemos acceder al menú general del programa 
(esquina superior izquierda) en Usuario > Preferencias. Esta acción nos 
solicitará cerrar las pestañas que tengamos abiertas.

Dentro del menú Preferencias deberemos entrar en la pestaña Usuario donde 
encontraremos varios campos rellenados y el campo contraseña en la esquina 
superior derecha oculta bajo puntos (el número de punto de coincide con el 
número de caracteres de la contraseña)

Podemos modificar la contraseña borrando el contenido del campo y escribiendo 
la nueva contraseña que deseemos (también se escribirá oculta). En validar los 
cambios con el botón De acuerdo nos solicitará la por última vez la antigua 
contraseña.
