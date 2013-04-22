==========
Producción
==========

Define los conceptos básicos para la gestión de la producción: lista de
materiales y orden de producción.

.. inheritref:: company/company:section:lista_de_materiales

Lista de materiales
===================

Es la lista de los productos y las cantidades necesarias para producir un
producto. A menudo se abrevia con las siglas LdM.

.. inheritref:: company/company:section:configuracion

Configuración
-------------

Para crear listas de materiales siga los siguientes pasos:

* Abra el menú |menu_bom_list|
* Haga clic en el botón **Crear un nuevo registro**.
* Asigne un nombre a la misma.
* Añada los productos, cantidades y unidades de medida de las líneas de entrada
  y salida.

.. |menu_bom_list| tryref:: production.menu_bom_list/complete_name

.. inheritref:: company/company:section:orden_de_produccion

Orden de producción
===================

Se define principalmente por un producto, una lista de materiales, una
ubicación, una cantidad y dos listas de movimientos:

* **Entradas**: Los movimientos entre el lugar de almacenamiento y el lugar de
  producción (tal como se define en el almacén) para los productos utilizados
  para producción.
* **Salidas**: Los movimientos entre el lugar de producción y el lugar de
  almacenamiento de los productos producidos.

La orden de producción puede estar en uno de los siguientes estados:

* **Pedido**: El sistema solicita la producción
* **Borrador**: Los movimientos de entrada y salida están en estado borrador.
* **En espera**: La producción está a la espera de llevarse a cabo y todos los
  movimientos se encuentran aún en borrador.
* **Reservado**: Se asignan los movimientos de entrada.
* **En Ejecución**: Los movimientos de entrada cambian a estado de realizado.
* **Realizado**: Los movimientos de salida cambian a estado de realizado.
* **Cancelado**: Todos los movimientos se cancelan.

El coste de la producción se calcula con la suma del precio de coste de todos
los productos entrantes. Si se selecciona un producto, tendrá el costo como
precio unitario. Tryton comprueba que todo el coste se reparte sobre el precio
unitario de movimientos de salida.

.. inheritref:: company/company:section:funcionamiento

Funcionamiento
--------------

Para ejecutar una order de producción, siga los siguientes pasos:

* Abra el menú |menu_production_list|
* Haga clic en el botón **Crear un nuevo registro**.
* En la pestaña **Información adicional** asigne la *Ubicación*.
* Añada la *Referencia*, los *Productos*, la *Lista de materiales (LdM)*, y la
  cantidad.
* Vaya cambiando el estado de la **Orden de producción** en función del estado
  de la misma.

.. |menu_production_list| tryref:: production.menu_production_list/complete_name
