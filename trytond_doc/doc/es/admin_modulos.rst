.. This file is part of Tryton.  The COPYRIGHT file at the top level of
.. this repository contains the full copyright notices and license terms.

=========================
Administración de módulos
=========================

Tryton incorpora una infinidad de módulos que añaden nuevas funcionalidades
(añadiendo nuevos campos a objetos existentes o creando objetos nuevos) o cambian
funcionalidades por defecto para que tengan un comportamiento distinto (funciones).

.. tip:: Tryton a parte de ser un ERP, es una herramienta de gestión de cualquier
         proceso, no necesariamente un proceso de una empresa.

-----------
Instalación
-----------

Para instalar un nuevo módulo iremos a **Administración/Módulos**.

.. important:: Antes de instalar cualquier módulo asegúrese que hace y si es lo
               deseado. Antes de instalar un módulo a la base de datos de producción,
               instale a la base de datos de **test** y testée. Sólo instale
               los módulos que necesite.

* **Administración/Módulos/Módulos** Busque el módulo deseado e instale.

Actualizar la lista de módulos
==============================

Para disponer de nuevos módulos instalados a su servidor de Tryton, un técnico
le deberá actualizar su base de datos con la opción **-u** (update)

Dependencias
============

Hay módulo que dependen de otros. Revise la pestaña **Dependencias** para más
información del módulo.

* Si estan ya **instalados**, se omiten. No se vuelven a instalar.
* Si **no estan instalados**, se instalaran ya que son requeridos.
* Si **no se encuentran**, los deberá buscar y instalar en el servidor de Tryton.

Características
===============

Una vez instalado el módulo ya dispondrá de nuevos campos o nuevos comportamientos
o funcionalidad de los módulos instalados. Consulte la documentación de cada módulo
en el `listado completo de módulos de Tryton`_

.. _listado completo de módulos de Tryton: modules.html

--------------
Desinstalación
--------------

Aunque Trtyon dispone de esta funcionalidad, no se recomienda esta acción a base
de datos de producción. Use una base de datos **test** para cualquier testeo.

.. important:: Evite la opción de desintalar módulos en bases de datos de producción.

La tablas de la base de datos dónde se guarden la información de los módulos
instalados **no** se eliminan y esta información queda para siempre en nuestra
base de datos pero sin consultar y estar disponible.
