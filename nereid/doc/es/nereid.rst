======
Nereid
======

.. inheritref:: nereid/nereid:section:sobre_nereid

Sobre Nereid
============

Nereid es una herramienta de desarrollo para aplicaciones web que se gestiona
mediante Tryton como herramienta de gestión.

El módulo de Nereid añade esta funcionalidad a Tryton y es puramente técnico.

Para la gestión de las partes disponibles de su web deberá acceder a cada apartado
específico. Por ejemplo, si disponemos de nuestra web un catálodo de productos,
en la sección **Productos** nos permitirá la gestión de ellos.

Si nuestra web permite una sección de **Blogs**, deberá instalar el módulo *Nereid Blog*
y acceder al apartado de gestión de Blogs para su gestión.

.. inheritref:: nereid/nereid:section:configuracion

Configuración
=============

Para la configuración de Flask y Nereid consulte la `documentación`_

.. _documentación: http://nereid.openlabs.co.in/docs/

Una vez instalado el módulo de Nereid a Trtyon, deberemos crear nuestro site. En
|menu_nereid_website| crearemos nuestro site:

* |name|: El nombre de nuestro dominio
* |url_map|: La estructura de URL de nuestra web
* |default_language|: Idioma por defecto
* |application_user|: Usuario de Tryton que realizará las acciones
* |guest_user|: Usuario invitado de Trtyon
* |countries|: Países disponibles en nuestra web

.. |menu_nereid_website| tryref:: nereid.menu_website_form/complete_name
.. |name| field:: nereid.website/name
.. |url_map| field:: nereid.website/url_map
.. |default_language| field:: nereid.website/default_language
.. |application_user| field:: nereid.website/application_user
.. |guest_user| field:: nereid.website/guest_user
.. |countries| field:: nereid.website/countries

.. inheritref:: nereid/nereid:section:ficheros_estaticos

Ficheros estáticos
==================

Desde Tryton también podemos añadir ficheros estáticos (imágenes, pdf, etc) para
que estén disponibles en nuestra web en el menú |menu_nereid_static|.

.. |menu_nereid_static| tryref:: nereid.menu_nereid_static/complete_name

Para el acceso de estos ficheros podrá en sus contenidos crear un enlace con la
siguiente ejemplo:

http://dominio.com/es//static-file/DIRECTORIO/NOMBRE_FICHERO.jpg

* DIRECTORIO: Nombre del directorio - minúsculas.
* NOMBRE_FICHERO.jpg: Nombre del fichero - minúsculas.

Recuerden que los nombres de los ficheros usar sólo carácteres az09 (alfanuméricos).
