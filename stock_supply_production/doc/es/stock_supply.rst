#:after:stock_supply/stock_supply:section:planificacion#

.. inheritref:: stock_supply/stock_supply:section:prevision_abastecimiento_stock

========================
Suministro de producción
========================

Añade mecanismos automáticos de suministro a través de solicitudes de
producción.

Solicitudes de producción
=========================

Una solicitud de producción es una producción en estado de solicitud. Define la
necesidad de producir un producto.

Reglas de abastecimiento
========================

Añade un nuevo tipo de regla de abastecimiento:

* **Producción**: Una regla de abastecimiento de producción define una
  ubicación de almacén. En el momento que el almacén quede por debajo de la
  cantidad mínima consignada, Tryton generará una *Solicitud de producción*.

El planificador crea las solicitudes de producción teniendo en cuenta los
niveles de existencias y las solicitudes existentes. Los niveles de existencias
se calculan en el *Período de suministro* definido en la configuración de
producción.

.. note:: Para que un producto pueda utilizar las reglas de abastecimiento,
          no debe ser comprable ni vendible.

Configuración
=============

Listas de Materiales
--------------------

Asigne o cree la **Lista de Materiales (LdM)** para los productos a producir.
Para ello, siga los siguientes pasos:

* Abra el menú |menu_main_product|.
* Abra la pestaña **LdM**
* Añada la *Lista de materiales* de fabricación de este producto.
* Si no existe ninguna lista de materiales puede crearla desde esta misma
  pestaña, o desde el menú |menu_bom_list| como se explica en la :ref:`configuración
  de las lista de materiales <production-bom>`

.. |menu_main_product| tryref:: product.menu_main_product/complete_name
.. |menu_bom_list| tryref:: production.menu_bom_list/complete_name

Reglas de abastecimiento
------------------------

Defina *reglas de abastecimiento* para las materias primas y para los productos
que deba producir. Para ello, siga los siguientes pasos:

* Abra el menú |menu_order_point_form|.
* Haga clic sobre el botón **Crear un nuevo registro**.
* Establezca el *Tipo* regla de abastecimiento a **Producción** en el caso de
  los productos a producir, y **Comprar** en el caso de los productos a
  comprar.
* Seleccione el producto que quiere comprar/producir en función de los
  seleccionado previamente.
* Abra la *Ubicación del almacén* y asigne una ubicación por defecto para
  la *Producción*.
* Rellene el resto de campos tal y como se explica en la configuración de las
  reglas de abastecimiento.

.. |menu_order_point_form| tryref:: stock_supply.menu_order_point_form/complete_name

Períodos de suministro
----------------------

Para definir el *Período de suministro* siga los siguientes pasos:

* Abra el menú |menu_production_configuration|.
* Establezca el período de suministro en número de días.

.. |menu_production_configuration| tryref:: production.menu_production_configuration/complete_name

Funcionamiento
==============

Una vez configuradas las listas de producción, las reglas de abastecimiento de
los productos a comprar y producir, los periodos de suministro de los mismos, y
asignadas las listas de materiales a los productos a fabricar, las solicitudes
se pueden generar de dos formas distintas:

Mediante el asistente
---------------------

Para generar **Solicitudes de producción** mediante el asistente, siga los
siguientes pasos:

* Abra el menú |menu_production_request_create|.
* Haga clic sobre el botón **Crear un nuevo registro**.
* Haga clic en crear.

.. |menu_production_request_create| tryref:: stock_supply_production.menu_production_request_create/complete_name

Mediante el planificador
------------------------

El planificador **Generar solicitudes de producción** se encarga de generar las
solicitudes de producción automáticamente en los periodos configurados en el
mismo.
