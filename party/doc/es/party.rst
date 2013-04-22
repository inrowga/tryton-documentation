================================
Terceros (clientes, proveedores)
================================

Un **tercero** puede ser un cliente, un proveedor, una persona física o jurídica,
una entidad, una fundación, etc. Aquí encontraremos cualquier contacto relacionado
con nuestra empresa, incluida esta misma.

Está definido por su nombre, un código, un idioma, un CIF/NIF, una categoría, el
mecanismo de contacto y una lista de direcciones.

Gestionará los terceos a |menu_terceros|. Según los módulos que disponga, la ficha
del tercero tendrá más o menos campos.

.. |menu_terceros| tryref:: party.menu_party_form/name

.. inheritref:: party/party:section:direcciones

Direcciones
===========

Un tercero puede disponer de varios direcciones. Dentro del formulario dispondrá
de varias direcciones relacionados con este tercero.

Una dirección está compuesta del nombre, la calle, el código postal, la ciudad,
el estado, una subdivisión (que en el caso de España puede ser la comunidad autónoma,
la provincia o la comarca). El campo secuencia permite ordenarlos.

.. image:: images/party-menu.png

.. note:: Para eliminar una dirección, lo haremos con el botón de eliminar de la
          dirección. No usaremos el menú desplegable que aparece cuando hacemos
          clic sobre botón de herramientas superior, ya que en ese caso
          eliminaríamos la empresa.

.. figure:: images/party-m2o-delete.png

   Eliminar campos dentro de la ficha

.. inheritref:: party/party:section:medios_de_contacto

Medios de contacto
=====================

El mecanismo de contacto está constituido de un tipo, un valor y un comentario.
El tipo puede ser:

* Teléfono
* Móvil
* Fax
* Correo electrónico
* Sitio web
* Skipe
* SIP
* IRC
* Jabber
* Otros

.. inheritref:: party/party:section:categoria

Categoría
=========

Una categoría está compuesta simplemente de un nombre, constituyendo las etiquetas
que se pueden asociar a un tercero. Las categorías se organizan en una estructura de árbol.

.. inheritref:: party/party:section:informes

Informes
========

Dispone de dos informes:

* El informe **Etiquetas** crea un documento con el nombre y direcciones de todos
  los terceros seleccionados que están pre-formateados para ser imprimidos en
  etiquetas que se puedan pegar en un sobre.

* El informe **Carta** crea un documento pre-rellenado con la cabecera de la
  compañía, la dirección del destinatario, la fecha, un saludo, un final y la
  firma del usuario que lanza el informe.
