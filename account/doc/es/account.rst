============
Contabilidad
============

------------------
Empezar a trabajar
------------------

El sistema contable de Tryton es una pieza más del sistema integrado de gestión
(ERP) de nuestra empresa u organización. Está pensado para trabajar
conjuntamente con los sistemas de ventas y compras de **Tryton** para evitar
duplicar procesos en la introducción de datos y para disponer de la información
contable en tiempo real. Esto permite enormes ventajas en nuestra
empresa/organización pues:

* Reduce el trabajo de nuestro departamento contable/financiero gracias a la
  reducción de duplicidades y errores.
* Permite tomar decisiones estratégicas en función de los balances contables
  reales.

El sistema contable financiero de **Tryton** es en realidad un motor de
contabilidad donde, una vez configurado adecuadamente, se le introduce sólo la
información imprescindible y él calcula de forma automática los resultados y
balances. Podríamos hacer un símil con un robot de cocina: Una vez programado
el robot de cocina (ejercicios, periodos, diarios, plan contable, impuestos,
pagos) y introducido los ingredientes (facturas, extractos bancarios, asientos
especiales) él automáticamente nos prepara nuestro plato culinario (calcula
facturas pagadas/pendientes mediante conciliación, balances contables, informes
de impuestos, ...).

.. note:: Hay que recordar que en Tryton se denomina *Empresa* a nuestra propia
          empresa y *Tercero* a cualquier empresa/organización/particular con la
          que mantenemos una relación (cliente, proveedor, asesor, cliente
          potencial, etc).

Antes de empezar a trabajar deberemos configurar el sistema según nuestras
necesidades. Para ello deberemos abrir un nuevo ejercicio fiscal, crear una nueva 
cuenta contable, un nuevo plan contable, crear los libros diarios que utilizaremos
y, en caso necesario, configurar los impuestos que utilizaremos. 

Abrir ejercicio fiscal
----------------------
El ejercicio fiscal tiene como función el acotar el inicio y cierre de los
diferentes libros que vamos a utilizar. Por regla general, el ejercicio fiscal suele
coincidir con el año natural. Para abrir un ejercicio fiscal debemos dirigirnos
al menú |menu_fiscalyear|, hacemos clic en el botón nuevo y rellenamos todos los
campos obligatorios: |name|, |start_date| y |end_date|. También podemos dar un
código al ejercicio fiscal, aunque esta campo tiene un carácter opcional.

.. inheritref:: account/account:paragraph:secuencias

En la pestaña *Secuencias* deberemos introducir la secuencia que queramos que 
se utilice para los asientos confirmados del periodo fiscal. Podemos elegir una
si la hemos creado previamente (:ref:`admin-secuencias`) o crear una clicando
sobre el icono *Nuevo*. 

.. Note:: Es imprescindible que la secuencia no se repita entre distintos
          ejercicios fiscales, es por eso que para cada uno de los distintos
          ejercicios que vayamos abriendo a lo largo del tiempo, deberemos crear
          una nueva secuencia.

Finalmente, una vez introducidos los parámetros generales y las secuencias. Podemos
volver a la pestaña *Períodos* y hacer clic en el botón *Crear períodos mensuales*.
Con esto ya tendremos un período para cada mes del año fiscal y todo asiento será 
siempre clasificado dentro de un período, debiendo coincidir su fecha con el 
intervalo de fechas correspondiente al dicho período.

.. Note:: No es recomendable utilizar períodos trimestrales porque en varios informes
          contables Tryton solamente nos permitirá seleccionar por períodos, y si 
          estos son trimestrales la concrección de los informes será menor. Es
          preferible hacer la división por meses y si necesitamos hacer alguna
          declaración trimestral, tan solo tendremos que unir peridos de tres en 
          tres.


.. |menu_fiscalyear| tryref:: account.menu_fiscalyear_form/complete_name
.. |name| field:: account.fiscalyear/name
.. |start_date| field:: account.fiscalyear/start_date
.. |end_date| field:: account.fiscalyear/end_date

.. _cuenta-nueva:

.. inheritref:: account/account:paragraph:cuenta

Crear una nueva cuenta contable
-------------------------------
Una cuenta contable es el lugar donde indicamos los cambios que se producen en
nuestros activos o pasivos durante un periodo concreto. Por lo que, por medio de
las cuentas, podemos analizar la evolución de nuestros activos, nuestras
obligaciones o las variaciones de nuestro capital.

Para crear una nueva cuenta debemos dirigirnos al menú |menu_account|. Clicaremos
en el botón *Nuevo* y podremos ir rellenando todos los datos que nos pide el sistema
para la creación de la nueva cuenta.

En primer lugar deberemos rellenar el |name_account| de esta nueva cuenta,
posteriormente deberemos darle un |code_account| a la cuenta que servirá para
indicarle al sistema de qué grupos va a depender esta cuenta. Los demás campos a 
rellenar son:

* |company_account|: Indicaremos la empresa en la que crearemos la cuenta.

* |parent_account|: De qué otra cuenta va a depender la nueva. 
  
* |kind_account|:  Indicaremos qué clase de cuenta que es, dependiendo si es una 
  cuenta de gastos o ingresos. *Vista* es para indicar que de esta cuenta dependerán
  varias más.

* |type_account|: Seleccionaremos el tipo de cuenta que será.

* |deferral_account|: Marcaremos el *tick* en caso de que la cuenta sea prorrogable 
  tras el cierre del ejercicio fiscal. Este campo nos permite indicar si el saldo
  de la cuenta debe ser arrastrado al período siguiente una vez cerrado el año.


* |reconcile_account|: En caso de que queramos que la cuenta sea conciliable.

.. *Tercero requerido:** Marcaremos el *tick* en caso de que queramos que sea obligatorio que se 
   indique el tercero al hacer apuntes. (altre mòdul)

.. **Conciliación bancaria:** Seleccionaremos esta opción en caso de que queramos que con los apuntes de 
   la cuenta se puedan hacer conciliaciones bancarias.

* |currency_account|: Por defecto nos indicará la moneda con la que se realizarán los apuntes.

* |taxes_account|: Seleccionaremos aquí, en caso de que queramos informar de impuestos 
  específicos para los apuntes que se añadan a la cuenta.
  
Una vez creadas las cuentas contables que necesitemos, podemos ir a |menu_contable| y configurar
las cuentas contables que utilizaremos por defecto para los pagos y los ingresos.


.. |menu_account| tryref:: account.menu_account_list/complete_name
.. |name_account| field:: account.account/name
.. |code_account| field:: account.account/code
.. |company_account| field:: account.account/company
.. |parent_account| field:: account.account/parent
.. |kind_account| field:: account.account/kind
.. |type_account| field:: account.account/type
.. |deferral_account| field:: account.account/deferral
.. |reconcile_account| field:: account.account/reconcile
.. |currency_account| field:: account.account/currency
.. |taxes_account| field:: account.account/taxes
.. |menu_contable| tryref:: account.menuitem_account_configuration/complete_name

.. inheritref:: account/account:section:nuevo_diario

Crear un nuevo diario
---------------------
Los libros diarios son libros donde se va estableciendo cronologicamente los registros
contables que se van produciendo en nuestra empresa. Para crear uno nuevo debemos acceder
por medio de la ruta |menu_journal|.

Nos aparecerá una lista con todos los diarios que tenemos, hacemos clic en *Nuevo*
y nos cambiará la vista para poder crear un diario nuevo. Aquí debemos seleccionar
el |name_journal|, |type_journal|, elegir qué clase de |sequence| se seguirá, la 
|credit_account| y la |debit_account|. Además podemos elegir también
si en este diario permitiremos que se cancelen asientos. 

A parte de los distintos |journal_type| que vienen por defecto en **Tryton**, podemos
crear nuevas tipologías según nuestras necesidades accediendo al menú |jour_type_menu|
y, tras clicar en *Nuevo*, indicar un |name_jour_type| y un |code_jour_type| para la 
nueva tipología de diario.

.. |menu_journal| tryref:: account.menu_journal_form/complete_name 
.. |name_journal| field:: account.journal/name
.. |type_journal| field:: account.journal/type
.. |sequence| field:: account.journal/sequence
.. |credit_account| field:: account.journal/credit_account
.. |debit_account| field:: account.journal/debit_account
.. |journal_type| tryref:: account.menu_journal_type_form/name
.. |jour_type_menu| tryref:: account.menu_journal_type_form/complete_name
.. |name_jour_type| field:: account.journal.type/name
.. |code_jour_type| field:: account.journal.type/code


Crear Plan contable
-------------------
.. inheritref:: account/account:paragraph:plan_contable

El plan contable es aquello que clasifica y organiza las distintas cuentas donde
se irá recogiendo el registro contable de las opereaciones que realice nuestra
empresa. Es por ello que una vez definidos los pasos previos según nuestras necesidades, podremos crear
nuestro plan contable. Para ello accederemos por medio de |crear_plan| y se nos 
abrirá un asistenete donde deberemos indicar la empresa sobre la que queremos
crear el plan y la |account_template| que utilizaremos para crearlo. 


.. |crear_plan| tryref:: account.menu_create_chart/complete_name
.. |account_template| model:: account.account.template
.. |actualizar_plan| tryref:: account.menu_update_chart/complete_name

.. Inheritref:: account/account:title:impuestos

Configurar los Impuestos 
------------------------

Para crear o modificar el sistema tributario podemos empezar accediendo a
|tax_group_menu| para dividir o agrupar los disintos tipos de impuestos. Estos
grupos se clasifican según si los impuestos que agrupan son referidos a la *venta*,
la *compra* o a *ambos*. En |tax_type_menu| podemos indicar y agrupar los impuestos
de una forma más concreta (ya sea por tipos de IVA deducible, devengado, etc).

Para crear un nuevo impuesto, deberemos acceder a |tax_menu| y al clicar en *Nuevo*
se nos abriá la vista de edición donde deberemos rellenar los distintos campos. 
|name_tax|, |description_tax|, el |group_tax|, el |type_tax| (si es un impuesto
con importe fijo deberemos también indicar el |amount_tax| y si seleccionamos
potcentaje deberemos indicar el |rate_tax| sobre el que se calculará el impuesto).
También deberemos indicar la |invoice_account_tax| y la |credit_note_account_tax|
en las que realizaremos las anotaciones contables. Además, en caso de que el 
impuesto que estemos generando tenga otros dependientes de él, lo deberemos indicar
en |child_tax|.

.. inheritref:: account/account:paragraph:impuestos_pestañas

Si accedemos a la pestaña *Código* podremos indica los distintos códigos de impuestos que 
utilizaremos para el impuesto.

En |rule_menu| podremos indicar los regímenes y reglas varias que agrupan los distintos
impuestos. Es otra forma distinta de agrupar los impuestos, pero en función de su 
régimen.

.. |tax_group_menu| tryref:: account.menu_tax_group_form/complete_name
.. |tax_type_menu| tryref:: account.menu_tax_code_list/complete_name
.. |tax_menu| tryref:: account.menu_tax_list/complete_name
.. |name_tax| field:: account.tax/name
.. |description_tax| field:: account.tax/description
.. |group_tax| field:: account.tax/group
.. |type_tax| field:: account.tax/type
.. |amount_tax| field:: account.tax/amount
.. |rate_tax| field:: account.tax/rate
.. |invoice_account_tax| field:: account.tax/invoice_account
.. |credit_note_account_tax| field:: account.tax/credit_note_account
.. |child_tax| field:: account.tax/childs

----------------
Gestión contable
----------------

Consultar libros diario
-----------------------

Si accedemos al menú |menu_diario_periodos| se nos abrirá una pestaña donde nos
aparecerán todos los diarios divididos en periodos, en los que que tenemos algún
apunte y actualmente estén abiertos. Si clicamos en cualquiera de ellos se nos
abrirá una nueva pestaña con todos los apuntes contables del diario.

En caso de que queramos acceder a algún diario cerrado, o a algún periodo cerrado 
de un diario, accederemos por medio de |menu_abre_diario| rellenando el nombre del 
diario y el periodo que queramos consultar. Una vez lo hayamos seleccionado se nos
abrirá una pestaña en la que nos aparecerán todos los apuntes contables del periodo
y diario elegido.

.. |menu_diario_periodos| tryref:: account.menu_journal_period_tree2/complete_name
.. |menu_abre_diario| tryref:: account.menu_open_journal/complete_name

Asientos contables
------------------
Cada anotación o registro que se realiza en los libros diarios o en las cuentas contables
son asientos. Para acceder a los asientos contables podemos hacerlo siguiendo la ruta
|menu_asientos|. Una vez nos aparezcan todos los asientos contables, podemos acceder a cada uno de ellos
para ver los apuntes o información del asiento.

.. |menu_asientos| tryref:: account.menu_move_form/complete_name

Conciliar apuntes
-----------------

???????

.. tryref:: account.menu_open_reconcile_lines/complete_name

--------------------------
Consulta planes contables
--------------------------
En cualquier momento podemos consultar el estado de nuestro plan contable accediendo a 
|menu_cplan| y se nos abrirá un asistente donde deberemos indicar qué plan contable queremos
consular. Podemos consultar cualquier plan ya cerrado de un ejercicio anterior o consultar 
el ejercicio actual.

Además, también podemos consultar el plan de código de impuestos para saber la cantidad de
impuestos soportados accediendo a |menu_cimp|.

.. |menu_cplan|  tryref:: account.menu_open_chart/complete_name
.. |menu_cimp| tryref:: account.menu_code_tax_open_chart/complete_name

-------------------------------
Cierre de la actividad contable
-------------------------------

.. _cerrar-periodos:

Cerrar periodos 
---------------

El cierre de períodos (sean mensuales o trimestrales) sirve para asegurarnos que no
modificamos la contabilidad de un período ya cerrado. Por ejemplo, si a mediados del
mes de abril damos por contabilizado completamente el mes de marzo (y con él todo el
trimestre) podemos cerrar el mes y Tryton nos garantizará que no contabilizamos nada
mas en este mes.

Además Tryton también nos permite cerrar no un período completo si no solamente un 
diario de un determinado período. Así, podemos asegurarnos que no imputamos más 
ingresos para el mes de marzo, mientras continuamos añadiendo gastos, por ejemplo.

Para cerrar un mes (|period|) y no permitir ningún tipo de cambio en la contabilidad
de dicho mes debemos ir al menú |menu_periods|. Ahí
deberemos seleccionar el mes que queremos cerrar y hacer clic en icono *Ejecutar
acción* y seleccionar *Cerrar período*.

Si lo que queremos es solamente evitar la creación y modificación de asientos en un diario y
período determinados debemos dirigirnos al menú |menu_jornals|. 
Ahí veremos todos los diarios - períodos que han sido ya abiertos (normalmente
porqué hemos hecho algún asiento en el mismo). Si encontramos el diario - período 
que queremos cerrar debemos seleccionarlo cerrar por medio del botón *Ejecutar acción*.

Si por el contrario queremos cerrar un diario - período en el cual no hemos 
contabilizado nada, podemos crear un registro nuevo indicando diario, período así 
como un nombre.

Una vez creado, podremos proceder a cerrarlo con la acción Cerrar diarios - períodos
antes mencionada.

.. |period| field:: account.fiscalyear/periods 
.. |menu_periods| tryref:: account.menu_period_form2/complete_name
.. |menu_jornals| tryref:: account.menu_journal_period_form/complete_name


Cerrar ejercicio fiscal
-----------------------
El cierre de un ejercicio fiscal suele constar del asiento de regularización, el asiento
de cierre, el de apertura del nuevo año, así como el bloqueo para no permitir la
contabilización de nuevos datos en el año cerrado. En Tryton solamente vamos a realizar
la primera y la última acción: el asiento de regularización y el bloqueo del año pero el
asiento de cierre y apertura no porque no son necesarios en el sistema, puesto que Tryton
arrastrará los saldos de las cuentas al año siguiente y una vez cerrado el año, **no** 
arrastrará los saldos de las cuentas de ingresos y gastos si estas están bien 
configuradas (:ref:`vea el apartado Crear una nueva cuenta contable para más información`).
Hay que tener en cuenta que **sí** que se van a arrastrar los saldos de las cuentas de 
ingresos y gastos mientras no se haya cerrado el año, puesto que el sistema intenta 
garantizar que el balance de situación está siempre cuadrado.


El asiento de regularización
~~~~~~~~~~~~~~~~~~~~~~~~~~~~
El primer paso para el cierre del ejercicio es realizar el asiento de regularización.
Para ello debemos acceder al menú |menu_regularizacion|. Este asistente creará el
asiento de regularización, cerrando el saldo de todas las cuentas que no tienen el 
campo |cierre| marcado (:ref:`cuenta-nueva`). En la pantalla que nos muestra el programa 
debemos indicarle el ejercicio a cerrar, el diario y el período donde contabilizarlo. 
El diario podemos crearlo desde la misma pantalla haciendo clic en el botón Nuevo 
del campo diario, si no existe. Si ya cerramos un año con el sistema podremos escoger
el mismo diario que el año anterior. Como podemos observar, el diario deberá ser de 
Tipo Situación.

El período también podemos crearlo con el botón Nuevo del acmpo Período del asistente
de regularización. La |start_date| y la |end_date| deberán ser la misma y coincidir con el 
último día del año fiscal al que pertenece. De nuevo, el |type| del período deberá ser
especial, en concreto deberá ser de tipo *Ajuste*, que es lo que le permitirá que las 
fechas del período se solapen con las fechas de otro período. En el ejemplo, la fecha 
es 31/12/2014 y se solapa con el período 2014-12.

Por útlimos deberemos indicar la cuenta a la cual se contabilizará el saldo de las 
cuentas de ingresos y gastos. Como podemos ver, Tryton admite poner el saldo en una 
cuenta distinta dependiendo de si el resultado es creditor o deudor.

.. view:: account.fiscalyear_balance_non_deferral_start_view_form

Cerrar/bloquear ejercicio fiscal
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
En el apartado :ref:`cerrar-periodos` explicamos como podemos ir cerrando períodos o 
diarios y períodos durante el año para evitar la contabilización de nuevos datos 
en unas fechas determinadas.
A parte de esto, Tryton provee una opción para realizar dicho cierre para todos los períodos 
del año. Para ello debemos ir al menú |menu_cierres|. Solamente tendremos que indicar
el ejercicio fiscal y pulsar en Cerrar.


.. |menu_regularizacion| tryref:: account.menu_balance_non_deferral/complete_name
.. |cierre| field:: account.account/deferral
.. |start_date| field:: account.period/start_date
.. |end_date| field:: account.period/end_date
.. |type| field:: account.period/type
.. |menu_cierres| tryref:: account.menu_close_fiscalyear/complete_name
