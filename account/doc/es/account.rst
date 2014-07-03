============
Contabilidad
============

.. inheritref:: account/account:section:introduccion_a_la_contabilidad

-----------------------------------------------------
Introducción a la contabilidad financiera con Tryton
-----------------------------------------------------

El sistema contable de Tryton es una pieza más del sistema integrado de gestión
(ERP) de nuestra empresa u organización. Está pensado para trabajar
conjuntamente con los sistemas de ventas y compras de Tryton para evitar
duplicar procesos en la introducción de datos y para disponer de la información
contable en tiempo real. Esto permite enormes ventajas en nuestra
empresa/organización pues:

* Reduce el trabajo de nuestro departamento contable/financiero gracias a la
  reducción de duplicidades y errores.
* Permite tomar decisiones estratégicas en función de los balances contables
  reales.

Si bien, sólo instalando el módulo **account** y **account_invocie**, se puede
llevar únicamente la gestión contable financiera de nuestra empresa o compañía
con Tryton, sacaremos más provecho de nuestra gestión integrada si también
instalamos otros módulos como **sale** y **purchase**, para poder obtener
automáticamente propuestas de facturas de cliente y proveedor desde los pedidos
de venta y compra o desde los albaranes de salida o entrada.

El sistema contable financiero de Tryton es en realidad un motor de
contabilidad donde, una vez configurado adecuadamente, se le introduce sólo la
información imprescindible y él calcula de forma automática los resultados y
balances. Podríamos hacer un símil con un robot de cocina: Una vez programado
el robot de cocina (ejercicios, periodos, diarios, plan contable, impuestos,
pagos) y introducido los ingredientes (facturas, extractos bancarios, asientos
especiales) él automáticamente nos prepara nuestro plato culinario (calcula
facturas pagadas/pendientes mediante conciliación, balances contables, informes
de impuestos, ...).

Recordar que en Tryton se denomina:

* **Empresa:** A nuestra propia empresa.
* **Tercero:** Cualquier empresa/organización/particular con la que mantenemos
  una relación (cliente, proveedor, asesor, cliente potencial, ...).

.. inheritref:: account/account:section:empresas_productos_y_informacion_contable

---------------------------------------------
Empresas/Productos y su información contable
---------------------------------------------

* Empresas y su información contable
* Productos y su información contable

.. inheritref:: account/account:section:asientos_y_movimientos

----------------------
Asientos y movimientos
----------------------

* Introduccion de asientos de forma manual
* Nominas: Generación y pago
* Asientos por extracto bancario
* Creación de modelos para asientos recurrentes
* Asientos periódicos/recurrentes

.. inheritref:: account/account:section:conciliacion_de_cuentas

------------------------
Conciliación de cuentas
------------------------

* Conciliación manual
* Conciliación automática
* Romper conciliación

.. inheritref:: account/account:section:otras_tareas_contables

----------------------
Otras tareas contables
----------------------

* Órdenes de pago y cobro (remesas)
* Efectos
* Recordatorios de pagos pendientes atrasados
* Informes contables
* Cierre del ejercicio fiscal
* Creación de anticipos
* Configuración multicompañía
* Generación del modelo AEAT 347
* Descuentos por pronto pago en ventas y compras
* Amortización de activos
* Gestión de efectos comerciales

.. inheritref:: account/account:section:configuracion_de_la_contabilidad_financiera

--------------------------------------------
Configuración de la contabilidad financiera
--------------------------------------------

.. inheritref:: account/account:bullet_list:account_configuration

* Ejercicios y períodos
* Diarios
* Plazos, tipos y modos de pago

.. inheritref:: account/account:section:plantillas_contables

Plantillas contables
====================

Las plantillas nos permiten realizar la configuración contable de nuestra empresa
de acuerdo a la normativa vigente, ya que están diseñadas según las directrices
marcadas por la misma.

Las plantillas contables de Tryton están formadas por:

* Plantilla para el plan contable
* Plantilla de cuentas contables
* Plantilla de impuestos
* Plantilla de códigos de impuestos
* Plantilla de posiciones fiscales

Son generadas al instalar los módulos correspondientes a la localización española
que instala los módulos habituales para la gestión contable de una PyME del Estado
Español.

Al generar el plan contable de nuestra empresa lo basaremos en el Plan General
Contable Español.

Para crear las cuentas contables a partir de la plantilla de plan contable correspondiente,
lo deberemos realizar con el asistente que se ejecuta automáticamente o mediante el menú
**Contabilidad/Configuración/Planes contables/Crear plan contable desde plantilla**.

Tendremos que especificar los siguientes datos:

* La plantilla del Plan Contable en que nos queramos basar. En el caso de la contabilidad
  española, Plantilla **Plan General Contable PYMES 2008** o **Plan General Contable 2008**
  (esta última es una simplificación de la primera, no tiene las cuentas del grupo 8 y 9).
* La compañía
* El número de dígitos (Módulo Account Code Digits) que tendrán las cuentas (normalmente
  entre 6 y 12, a una PyME le suelen bastar con 8). El número de dígitos viene definido
  en la configuración de la contabilidad **Contabilidad/Configuración/Configuración
  contable/Número de dígitos cuenta**.

.. inheritref:: account/account:section:multicompania

Multicompañía
-------------

Si gestionamos en Tryton una multicompañía de compañías españolas, se pueden generar
los distintos planes contables de cada empresa a partir de la misma plantilla.

.. note:: La ejecución de **Crear plan contable desde plantilla** se debe ejecutar
          por empresa que esté el usuario. Si queremos crear un plan contable a
          la *Empresa B*, el usuario a sus preferencias debe estar en esta empresa.
          Si se encuentra en otra empresa, no podrá crear el plan contable debido
          a permisos de acceso.

* Planes y cuentas contables
* Impuestos
