============
Contabilidad
============

------------------
Empezar a trabajar
------------------

El sistema contable de **Tryton** es una pieza más del sistema integrado de
gestión (ERP) de nuestra empresa u organización. Está pensado para trabajar
conjuntamente con los sistemas de ventas y compras de **Tryton** para evitar
duplicar procesos en la introducción de datos y para disponer de la información
contable en tiempo real. Esto permite enormes ventajas en nuestra
empresa/organización pues:

* Reduce el trabajo de nuestro departamento contable/financiero gracias a la
  reducción de duplicidades y errores.
* Permite tomar decisiones estratégicas en función de los balances contables
  reales.

El sistema contable financiero de **Tryton** es en realidad un motor de
contabilidad dónde, una vez configurado adecuadamente, se le introduce sólo la
información imprescindible y él calcula de forma automática los resultados y
balances. Podríamos hacer un símil con un robot de cocina: Una vez programado
el robot de cocina (ejercicios, periodos, diarios, plan contable, impuestos,
pagos, etc.) e introducido los ingredientes (facturas, extractos bancarios,
asientos especiales, etc.) él automáticamente nos prepara nuestro plato
culinario (calcula facturas pagadas/pendientes mediante conciliación, balances
contables, informes de impuestos...).

.. note:: Hay que recordar que en **Tryton** se denomina *Empresa* a nuestra
          propia empresa y *Tercero* a cualquier
          empresa/organización/particular con la que mantenemos una relación
          (cliente, proveedor, asesor, cliente potencial, etc).

Antes de empezar a trabajar deberemos configurar contablemente el sistema según
nuestras necesidades. Para ello deberemos abrir un nuevo ejercicio fiscal,
crear un nuevo plan contable y nuevas cuentas contables, crear los libros
diarios que utilizaremos y, en caso necesario, configurar los impuestos con los
que trabajaremos.

Abrir ejercicio fiscal
----------------------
El ejercicio fiscal, que por regla general suele coincidir con el año natural,
tiene como función acotar el inicio y cierre de los diferentes libros que
vamos a utilizar. Además limita temporalmente las anotaciones contables que
podamos introducir en el sistema, de manera que hasta que no se abra
el ejercicio fiscal (y los correspondientes periodos) no se podrá confirmar
ninguna factura (ni ningún asiento contable) fechada en ese año. Por ejemplo,
no se podrá confirmar ninguna factura fechada en el 2015 hasta que no se abra
un ejercicio fiscal con inicio fiscal 01/01/2015 y fianl fiscal
31/12/2015.

Para abrir un ejercicio fiscal debemos dirigirnos al menú año fiscal,
hacemos clic en el botón nuevo y rellenamos todos los campos obligatorios:
nombre, inicio fiscal y final fiscal. Si lo deseamos, también podemos dar
un código al ejercicio fiscal, aunque este campo tiene un carácter opcional.

.. Note:: Normalmente, solemos poner el año al que corresponde el ejercicio
   fiscal en nombre y en inicio fiscal y final fiscal, la fecha de inicio
   y fin del año natural.


.. view:: account.fiscalyear_view_form

   Vista del formulario del Ejercicio fiscal

Por otro lado, **Tryton** permite utilizar la misma secuencia de facturas para
las facturas de cliente, proveedor, abonos de cliente y abonos de proveedor
pero esto no es válido bajo la normativa española. Así que, si nuestra empresa
se rige por esta legislación, deberemos crear una serie exclusiva para nuestra
facturación.

En la pestaña *Secuencias* deberemos introducir la secuencia que queramos que
se utilice para los asientos y las distintas facturas confirmadas del periodo
fiscal. Podemos elegir una secuencia creada previamente o crear una clicando
sobre el icono *Nuevo* (:ref:`admin-secuencias`). Es imprescindible a nivel
contable que la secuencia no se repita entre distintos ejercicios fiscales, por
lo que, para cada uno de los distintos ejercicios que vayamos abriendo a lo
largo del tiempo, deberemos crear nuevas secuencias.

Finalmente, una vez introducidos los parámetros generales y las secuencias,
podemos volver a la pestaña *Períodos* y hacer clic en el botón *Crear períodos
mensuales*. Con esto se nos generará un período para cada mes del año fiscal y,
cuando desarrollemos nuestra actividad contable, todo asiento será siempre
clasificado dentro de un período teniendo en cuenta su data.

.. Note:: No es recomendable utilizar períodos trimestrales porque en varios
          informes contables **Tryton** solamente nos permitirá seleccionar por
          períodos, y si estos son trimestrales la concreción de los informes
          será menor. Es preferible hacer la división por meses y si
          necesitamos hacer alguna declaración trimestral, tan solo tendremos
          que unir periodos de tres en tres.


Crear una nueva cuenta contable
-------------------------------

Una cuenta contable es el lugar donde indicamos los cambios que se producen en
nuestros activos o pasivos durante un periodo concreto. Estos cambios suelen
ser agrupados en distintas cuentas contables según su naturaleza, por lo que,
por medio de las cuentas, podemos analizar la evolución de nuestros activos,
nuestras obligaciones o las variaciones de nuestro capital. Para crear una
nueva cuenta debemos dirigirnos al menú contabilidad y clicar en el botón
*Nuevo*.

.. view:: account.account_view_form

   Vista formulario de la cuentas contable

En primer lugar deberemos rellenar la cabecera del formulario que se nos
abrirá, indicando el nombre y el código de esta nueva cuenta.
Si le ponemos un código numérico, el código  nos servirá para
clasificar la cuenta e indicarle al sistema de qué grupos va a depender.

Una vez completada la cabecera, podemos ir rellenando el resto de campos según
el carácter que le queramos dar a la nueva cuenta contable:

* Empresa: Indicaremos para cual de nuestras empresas crearemos la
  cuenta.

* Padre: En caso de que la cuenta que estamos creando dependa de
  otra, lo deberemos indicar aquí.
#Modificar
* |kind_account|:  En este campo seleccionaremos de qué tipo será esta
  nueva cuenta. Si indicamos en este campo *Vista* le estaremos indicando al
  sistema que esta cuenta agrupará otras cuentas. El resto de tipologías que
  podemos seleccionar son: *A cobrar*, *A pagar*, *Existencias*, *Gastos*,
  *Ingresos* y *Otros*.

* Cierre: Marcaremos el *tick* en caso de que la cuenta sea
  prorrogable tras el cierre del ejercicio fiscal. Este campo nos permite
  indicar si el saldo de la cuenta debe ser arrastrado al período siguiente
  una vez cerrado el año.

* Conciliar: En caso de que queramos que la cuenta sea conciliable.

* Tercer obligatorio: Marcaremos el *tick* en caso de que queramos que sea
  obligatorio que se indique el tercero al hacer apuntes.

* Moneda: Por defecto nos indicará la moneda configurada por
  defecto para la contabilidad de la empresa.

* Moneda secundaria: Si indicamos una moneda secundaria, cuando
  vayamos a ver los extractos de la cuenta que estamos creando, además de los
  importes con la moneda principal, nos aparecerán también una columna
  indicando la conversión de los importes a la moneda secundaria
  seleccionada.

* Impuestos: Seleccionaremos aquí, en caso de que queramos informar de
  impuestos específicos para los apuntes que se añadan a la cuenta.

* Hijos: En caso de que queramos que otras cuentas dependan de la
  que estamos creando lo podremos indicar o crear otras cuentas nuevas por
  medio de este campo.

* Cierres: En esta pestaña se nos irán indicando, en caso de tener
  marcado el tick del campo cierre y conforme vayamos cerrando
  ejercicios fiscales, los importes del debe y haber del ejercicio fiscal al
  cierre de este.

.. Important:: Una vez tengamos creadas las cuentas contables que necesitemos,
   podremos ir al menú contable y configurar las cuentas que
   utilizaremos por defecto para los pagos y los ingresos.

Modificar el campo "Padre"
--------------------------

En Tryton es habitual encontrar datos estructurados en forma de “padres e hijos”
o “árbol”. Esto lo podemos encontrar, por ejemplo, en:

 * La estructura de empresas (menú Terceros > Configuración > Empresas)
 * El plan de cuentas (menú Configuración > Planes contables > Cuentas)
 * En categorías de terceros (menú Terceros > Categorías) y productos (menú
   Productos > Categorías)

En todos estos casos podremos ver que podemos acceder a la información mediante
dos entradas de menú. La primera con un icono escalado, en forma de árbol, y la
segunda, que la encontramos dentro de la primera, con un icono normal de
formulario.

Entrando en el primer caso, podremos ver la información en forma de árbol:

.. captura de la imagen

Mientras que en la segunda podremos verla en forma de lista:

.. captura de la imagen

Desde ambas pantallas podremos consultar y modificar información pero el
comportamiento de ambas es distinto:

 * En la vista tipo árbol podremos arrastrar y soltar (drag&drop) para
   establecer el padre. Esto no será posible en la vista tipo lista (la segunda)
 * En la vista tipo árbol no podremos cambiar el padre cuando entremos en la
   ficha / formulario.
 * En la vista tipo árbol solamente nos buscará en los elementos del primer
   nivel. En los subniveles aparecerán todos.


Crear un nuevo diario
---------------------
Los libros diarios son libros donde se van estableciendo cronológicamente los
registros contables que se van produciendo en nuestra empresa. Para crear uno
nuevo debemos acceder por medio de la ruta |menu_journal| y hacer clic en el
icono *Nuevo*.

.. view:: account.journal_view_form

   Vista del formulario de un nuevo Diario

En el formulario que se nos abrirá, deberemos seleccionar el nombre,
el tipo , elegir qué clase de secuencia se seguirá (podemos crear una
nueva secuencia o elegir una ya creada (:ref:`admin-secuencias`)), la
haber y la debe. Además podemos elegir también si en este
diario permitiremos que se cancelen asientos.
Una vez rellenados los campos podremos guardar el diario y ya lo tendremos
operativo para empezar a realizar apuntes contables en él.


Crear un plan contable
----------------------

El plan contable es aquello que clasifica y organiza las distintas cuentas
donde se irá recogiendo el registro contable de las operaciones que realice
nuestra empresa. Es por esto que una vez definidos los pasos previos según
nuestros intereses, podremos crear nuestro plan contable. Para ello
accederemos por medio de |menu_create_chart| y se nos abrirá un asistente 
donde deberemos indicar la empresa sobre la que queremos crear el plan y la
plantilla que utilizaremos para crearlo (por defecto el sistema tiene
ya generada la plantilla *Plan de tipos de cuenta mínimo* aunque también
podemos instalar el *Plan General de Contabilidad* o crear una plantilla
personalizada por medio del menú |menu_template_account|). Una vez indicados
estos campos, clicamos en *Crear* y se nos abrirá una nueva ventana donde
podremos indicar la cuenta a pagar por defecto  y la cuenta a cobrar por defecto
que utilizaremos para el plan contable.

Si clicamos de nuevo en *Crear* el sistema nos creará el nuevo Plan contable que,
posteriormente, podremos consultar por medio de |menu_open_chart|.

.. |menu_create_chart| tryref:: account.menu_create_chart/complete_name
.. |account_template| model:: account.account.template
.. |actualizar_plan| tryref:: account.menu_update_chart/complete_name
.. |menu_template_account| tryref:: account.menu_account_type_template_tree/complete_name
.. |plan_account_payable| field:: account.create_chart.properties/account_payable
.. |plan_account_receivable| field:: account.create_chart.properties/account_receivable

Configurar impuestos
--------------------

Para crear o modificar el sistema tributario de nuestro sistema deberemos
acceder en primer lugar a |tax_group_menu| para crear los grupos donde
posteriormente asociaremos los distintos tipos de impuestos que iremos
generando. Estos grupos se clasifican según si los impuestos se graban durante
la *venta*, la *compra* o durante *ambos*.

.. view:: account.tax_view_form

   Vista de formulario de un Impuesto


Para crear un nuevo impuesto, deberemos acceder a |tax_menu| y al clicar en
*Nuevo* se nos abrirá la vista de edición donde deberemos rellenar los
distintos campos para poder configurar el impuesto. Deberemos rellenar el
nombre, la descripción, el grupo al que pertenece, el
tipo (si indicamos aquí que es un impuesto con importe fijo también
deberemos indicar el importe, si, por el contrario, seleccionamos
*Porcentaje* deberemos indicar el pordentaje sobre el que se calculará el
impuesto). También deberemos indicar la cuenta de factura y
la cuenta de abono en las que realizaremos las anotaciones contables.
Además, en caso de que el impuesto que estemos generando tenga otros
dependientes de él, lo deberemos indicar en los hijos.

Si accedemos a la pestaña *Código* podremos indica los distintos códigos de
impuestos que utilizaremos para el impuesto.

En |rule_menu| podremos indicar los regímenes y reglas varias que agrupan los
distintos impuestos. Tendremos también otra forma distinta de agrupar los
impuestos, pero en función de su régimen.

.. |tax_group_menu| tryref:: account.menu_tax_group_form/complete_name
.. |tax_type_menu| tryref:: account.menu_tax_code_list/complete_name
.. |tax_menu| tryref:: account.menu_tax_list/complete_name
.. |rule_menu| tryref:: account.menu_tax_rule_form/complete_name

Configurar plazos de pago
-------------------------

Para crear o configurar los plazos de pago que posteriormente podremos aplicar
a nuestros clientes o proveedores, accederemos a
|menu_payment_terms_configuration| y, tras clicar en *Nuevo*, se nos abrirá el
formulario de edición de los plazos de pago. En él deberemos
indicar un nombre y rellenar al menos una línea de plazo de pago. Hay que tener
en cuenta que cada plazo de pago se compone de una o varias , estas
 nos indicarán cuándo y cómo se realizará el pago. Además, la cantidad
de  que compongan el plazo nos indicará cuántos pagos se deberán hacer.
Por ejemplo, si un pago es a 30 días, este plazo de pago sólo tendrá una
línea, en cambio, si el plazo de pago se realiza a 15 y a 30 días, se deberán
crear dos líneas, una para el pago a 15 días y otra para el pago a 30 días.

Cuando accedamos a crear una nueva línea, los campos que tendremos que
rellenar son:

* tipo: Donde podemos escoger entre:
    * *Fijo*: Es un valor fijo, siempre será el mismo sea cual sea el importe
      total a pagar, por lo que no dependerá de nada. Al seleccionar esta
      opción aparecerán dos campos nuevos:

           * importe: Indicaremos el importe fijo que se deberá de pagar.
           * moneda: La moneda que se usará para realizar el pago.

    * *Porcentaje sobre remanente*: Calculará el importe a pagar según un
      porcentaje aplicado sobre la cantidad que queda pendiente de pago.
    * *Porcentaje sobre total*: Calculará el importe a pagar según un
      porcentaje sobre el valor total de la factura. Al seleccionar esta opción
      o la anterior aparecerán dos campos nuevos:

          * porcentaje: Indicaremos aquí el valor en % de 0 a 100 que
            queremos que se aplique al total o al remanente.
          * divisor: Este campo se nos rellenará automáticamente si
            indicamos previamente el porcentaje. En caso de rellenar este
            campo primero, el que se rellenará automáticamente será el campo
            porcentaje. Esto se debe a que ambos campos están relacionados e
            indican lo mismo pero desde distintos puntos de vista. En este
            campo podremos indicar el divisor que se utilizará para realizar
            el cálculo del importe, o, dicho de otro modo, deberemos indicar
            por qué número queremos que se divida el total o remanente para
            calcular el importe a pagar. Por ejemplo, si indicamos en el campo
            porcentaje que se calcule sobre el 50 %, el campo divisor se
            nos rellenará con el número 2, ya que es lo mismo aplicar el 50 %
            a un importe que dividirlo por 2.

    * Remanente: El total de lo que queda por pagar, le resta del total lo ya
      pagado. Siempre que configuremos los plazos con una sola línea, deberemos
      escoger esta tipología, ya que al no haber ningún pago previo se realizará
      el pago sobre el total. Además, cuando creemos plazos con varias ,
      la última siempre deberá ser de esta tipología.

Y por cada tipo de línea de pago, indicaremos sus *Incrementos*:

* mes, setmanas y días: Indicaremos cuántos meses, semanas y días pasarán
  para generar el pago de la línea del plazo que estamos creando.
* mes, día de la setmana y día: Indicaremos el mes, día de la semana o día del
  mes exacto en el que se realizará el pago de esta línea.

Veamos algunos ejemplos de cómo configurar estas :

* **Pago a 30 días**. Sólo crearemos una línea:

  * tipo: Remanente
  * mes: 0
  * setmanas: 0
  * días: 30

* **Pago a 15/30 días**. Crearemos dos líneas:

  * Primera línea:

    * tipo: Porcentaje sobre total
    * porcentaje: 50
    * divisor: 2
    * mes: 0
    * setmanas: 0
    * días: 15

  * Segunda línea:

    * tipo: Remanente
    * mes: 0
    * setmanas: 0
    * días: 30

* **Pago el 1 de cada mes**. Crearemos una línea:

    * tipo: Remanente
    * día: 1
    * Dejaremos el resto de campos a 0.

Podemos especificar para cada tercero un plazo de pago desde la pestaña
**Contabilidad** de la ficha del propio tercero. En ella podremos indicar los
plazos para las ventas (cliente) y para las compras (proveedor) que le
realicemos.


.. |menu_payment_terms_configuration| tryref:: account_invoice.menu_payment_terms_configuration/complete_name

Amortización de activos
=======================

.. toctree::
   :maxdepth: 2

   ../../../account_asset/doc/es/account_asset

Pagos y cobros
==============

.. toctree::
   :maxdepth: 3

   ../../../account_payment/doc/es/account_payament

SEPA
====

.. toctree::
   :maxdepth: 3

   ../../../account_payment_sepa/doc/es/account_payament_sepa.rst

----------------
Gestión contable
----------------

Consultar libros diario
-----------------------

Si accedemos al menú Diarios - Períodos  se nos abrirá una pestaña donde nos
aparecerá un listado con todos los diarios, divididos en periodos, en los que
que hemos realizado algún apunte y permanecen todavía abiertos (hay que tener
en cuenta que si en algún periodo de algún diario no hay ninguna anotación, o
el periodo del diario está cerrado, no nos aparecerá en este listado). Si
clicamos en cualquiera de ellos se nos abrirá una nueva pestaña con todos los
apuntes contables anotados en el diario.

En caso de que queramos acceder a algún diario cerrado, o a algún periodo
cerrado de un diario, accederemos por medio del menu diario y se nos
abrirá una asistente donde deberemos rellenar el campo diario con el
nombre del diario y el periodo inicial con el periodo que queramos consultar. 
Una vez lo hayamos seleccionado se nos abrirá una pestaña en la que nos 
aparecerán todos los apuntes contables del periodo inicial y diarios elegidos.


Consultar asientos contables
----------------------------

Para **Tryton** un asiento contable se compone de varios apuntes que se anotan
en distintas cuentas contables. Conforme se vaya desarrollando nuestra
práctica contable, se nos irán generando un gran número de asientos y apuntes
que podremos consultar por medio de |menu_move|. Desde el listado que se nos
abrirá, podremos acceder a cada uno de los asientos contables para ver los
apuntes de los que se compone, así como la información concreta del asiento.

.. |menu_move| tryref:: account.menu_move_form/complete_name

Reclamaciones
=============
.. toctree::
   :maxdepth: 2

   ../../../account_dunning/doc/es/account_dunning

Extractos
=========
.. toctree::
   :maxdepth: 2

   ../../../account_statement/doc/es/account_statement

=========================
Definir planes analíticos
=========================

Los planes analíticos nos permiten controlar y analizar las cuentas de nuestra
empresa (entradas, salidas y balances) siguiendo una estructura de cuentas
definida por nosotros. Un ejemplo típico es estructurar las cuentas por
departamento y , por ejemplo, el departamento comercial dividido por comercial.

.. Captura de árbol de cuentas analíticas con más de una jerarquía,
   preferiblemente siguiendo el ejemplo comentado. Listado jerárquico de
   cuentas analíticas que encontramos en Contabilidad/ Configuración/
   Contabilidad analítica/ Cuentas analíticas

La contabilidad analítica en Tryton es **multi jerárquica**. Esto quiere decir
que podemos tener varios *planes analíticos*. Cada jerarquía tiene una cuenta
raíz, estas son completamente independientes y deberían ser completas.

Siguiendo el ejemplo, si nuestra empresa está muy enfocada a productos nos
puede interesar tener la *típica* visión **por departamento** pero también
tenerla **por producto**, registrando la aportación de cada departamento a cada
producto. Así, una visita comercial para un producto concreto añadirá su coste
al departamento comercial en la jerarquía *por departamento* y también en la
cuenta de producto en la jerarquía *por producto*.

Crear una nueva cuenta
----------------------

Crearemos las cuentas nuevas des del listado *normal* de cuentas analíticas que
encontramos en la entrada de menú Contabilidad/ Configuración/ Contabilidad
analítica/ Cuentas analíticas/ Cuentas analíticas.

.. Captura de imagen de formulario de nueva cuenta analítica.

Si estamos creando una jerarquía nueva elegiremos el **tipo** de cuenta
**Raíz**. Si queremos añadir una cuenta a una jerarquía existente deberemos
elegir primero la **raíz** de esta y luego la cuenta **padre**.

Las cuentas **Vista** son cuentas que no aceptan entradas asociadas
directamente a ellas y sirven para agrupar subcuentas (las cuentas *Raíz* en
este sentido son como una cuenta *Vista*). Por ejemplo, si en una parte de
nuestro plan analítico tenemos cuentas para cada proyecto, posiblemente nos
interesará una cuenta *Proyectos*, para ver fácilmente el balance sumado de
todos los proyectos, pero todos los gastos/ingresos deben ir a un proyecto
concreto.

Conciliar apuntes
-----------------

Recordemos que, para el sistema, conciliar consiste en enlazar un
apunte contable con el inverso que genera. Si generamos un apunte contable
contabilizando un servicio que realizamos, el apunte que genera el pago de
este servicio es el que tendría que conciliar el apunte del servicio en sí.
Hay que indicar también que la conciliación no es indispensable en la
práctica contable, pero nos ayuda en el cuadre de nuestras cuentas al
indicarnos qué apuntes están compensados con un pago o cobro y cuales no.

Aunque **Tryton** nos ofrece asistentes que nos ayudan en la conciliación,
podemos realizarla manualmente accediendo al diario o al extracto de cuenta
en el que se hayan anotado los apuntes que queremos conciliar, seleccionarlos
todos manteniendo apretado el botón *Ctrl* de nuestro teclado y, clicando en
el icono *Ejecutar acción*, seleccionar la opción *Conciliar apuntes*. En caso
de que queramos desconciliar dos apuntes conciliados previamente, lo
realizaríamos de la misma manera, pero seleccionando *Desconciliar apuntes* en
el menú.

Otros formas de conciliar apuntes són:

* Desde |menu_reconcile| se ejecuta un asistente que te va mostrando distintas
  propuestas con posibles apuntes a conciliar, pudiendo saltarlas si hace falta.
  Las propuestas las hace el programa, tu solo debes clicar botones de conciliar
  y saltar.
* A |menu_move_line_form| se puedes buscar apuntes por tercero y/o cuenta y conciliar.
  También se disponde de la pestaña de "Efectos con apuntes inversos" que solo muestra
  posibles conciliaciones.
* Abrir los apuntes a pagar-cobrar desde un tercero en concreto, con el botón "Relacionado".
  Y a partir de ahí podemos conciliar.
* Si se trabaja con extractos bancarios, una vez importados, se hacen las conciliaciones
  automáticas cuando se contabiliza una línea de extracto bancario.

.. Note:: Tenemos que tener en cuenta, tal y como hemos visto en
   :ref:`cuenta-nueva`, que solo podremos conciliar apuntes de cuentas
   contables que tengan marcado el campo |reconcile_account|.

.. |menu_reconcile|  tryref:: account.menu_reconcile/complete_name
.. |menu_move_line_form|  tryref:: account_payment.menu_move_line_form/complete_name


Consulta planes contables
--------------------------

En cualquier momento podemos consultar el estado de nuestro plan contable
accediendo a |menu_open_chart| y viendo los saldos totales o concretos de. Se
nos abrirá un asistente donde deberemos indicar el ejercicio fiscal del plan
contable que queremos consultar y, tras clicar en *Abrir* accederemos al plan
contable (o planes si tenemos más de uno para el ejercicio fiscal). Desde esta
pestaña podremos acceder también a cada una de las cuentas que conforman el
plan contable y a los apuntes inscritos en cada una de las cuentas contables
haciendo doble clic sobre ellas.

.. view:: account.open_chart_start_view_form

   Vista formulario del submenú Abrir plan contable

Además, también podemos consultar el *Plan de código de impuestos* para saber
la cantidad de impuestos soportados y devengados. Para ello accederemos a
|menu_cimp| y en el asistente que se nos abrirá seleccionaremos el/los
periodo/s sobre los que queramos realizar la consulta.

.. |menu_open_chart|  tryref:: account.menu_open_chart/complete_name
.. |menu_cimp| tryref:: account.menu_code_tax_open_chart/complete_name

-------------------------------
Cierre de la actividad contable
-------------------------------

.. _cerrar-periodos:

Cerrar períodos
---------------

El cierre de período (sean mensuales o trimestrales) sirve para asegurarnos
que no modificamos la contabilidad de un período en el que ya no se deberían
que hacer anotaciones. Por ejemplo, si a mediados del mes de abril damos por
contabilizado completamente el mes de marzo (y con él todo el trimestre)
podemos cerrar el mes y **Tryton** nos garantizará que no contabilizamos, ni
nosotros ni ningún otro compañero, nada más en este mes.

Además **Tryton** también nos permite cerrar no un período completo si no
solamente un diario de un determinado período. Así, podemos asegurarnos que no
imputamos más ingresos para el mes de marzo, mientras continuamos añadiendo
gastos, por ejemplo.

Para cerrar un período y no permitir ningún tipo de cambio en la
contabilidad de dicho mes debemos ir al menú Períodos Ahí deberemos
seleccionar el mes que queramos cerrar y hacer clic en icono *Ejecutar
acción* y seleccionar *Cerrar período*.

Si lo que queremos es solamente evitar la creación y modificación de asientos
en un diario y período determinados debemos dirigirnos al menú Diarios.
Ahí veremos todos los diarios - períodos que han sido ya abiertos (normalmente
porque hemos hecho algún asiento en el mismo). Si encontramos el
diario - período que queremos cerrar debemos seleccionarlo cerrar por medio del
botón *Ejecutar acción*.

Si por el contrario queremos cerrar un diario - período en el cual no hemos
contabilizado nada, podemos crear un registro nuevo indicando diario, período
así como un nombre. Una vez creado, podremos proceder a cerrarlo con la acción
*Cerrar diarios - períodos* antes mencionada.


Cerrar ejercicio fiscal
-----------------------

En contabilidad, el cierre de un ejercicio fiscal suele constar del asiento de
regularización, el asiento de cierre y el de apertura del nuevo año, así como el
bloqueo para no permitir la contabilización de nuevos datos en el año cerrado.
En **Tryton** solamente vamos a realizar la primera y la última acción: el
asiento de regularización y el bloqueo del año pero el asiento de cierre y
apertura no porque no son necesarios en el sistema, puesto que **Tryton**
arrastrará los saldos de las cuentas al año siguiente y una vez cerrado el año.
No arrastrará los saldos de las cuentas de ingresos y gastos si estas están
bien configuradas, tal y como veremos a continuación.

.. Note:: Hay que tener en cuenta que sí que se van a arrastrar los saldos
   de las cuentas de ingresos y gastos mientras no se haya cerrado el año,
   puesto que el sistema intenta garantizar que el balance de situación está
   siempre cuadrado.


El asiento de regularización
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

El primer paso para el cierre del ejercicio es realizar el asiento de
regularización. Para ello debemos acceder al menú regularización. Este
asistente creará el asiento de regularización, cerrando el saldo de todas las
cuentas que no tienen el campo cierre marcado (:ref:`cuenta-nueva`).
En la pantalla que nos muestra el programa debemos indicarle el ejercicio a
cerrar, el diario y el período donde contabilizarlo.

.. view:: account.fiscalyear_balance_non_deferral_start_view_form

   Vista con el formulario a rellenar para crear el asiento de regularización

* El diario deberá ser de tipo *Situación* y, en caso de no tener
  ninguno creado, podremos generarlo desde la misma pantalla haciendo clic en
  el botón *Nuevo* del campo diario. Si tenemos en **Tryton** un
  año anterior cerrado, podremos escoger el mismo diario que se utilizó para el
  anterior cierre.

* El período también podemos crearlo clicando en el botón *Nuevo* del
  propio campo. La fecha de inicio y la fecha final deberán ser la misma y
  coincidir con el último día del año fiscal al que pertenece. De nuevo, el
  tipo del período deberá ser especial, en concreto deberá ser de tipo
  *Ajuste*, que es el único tipo al que el sistema le permite que las fechas
  propias del período se solapen con las fechas de otro período.

* Por último deberemos indicar la cuenta a la cual se contabilizará el saldo de
  las cuentas de ingresos y gastos en los campos cuenta haber y
  cuenta deber. Como podemos ver, **Tryton** admite poner el saldo en una
  cuenta distinta dependiendo de si el resultado es creditor o deudor, aunque
  si lo preferimos podemos poner la misma cuenta en ambos campos para que no se
  realice esta distinción.


Cerrar/bloquear ejercicio fiscal
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Por último ya solo nos quedará cerrar el ejercicio fiscal. Este paso no tiene
efectos contables, simplemente evita que se realicen nuevos apuntes contables
en cualquiera de los periodos que integra el ejercicio fiscal una vez cerrado.
Como hemos visto en  el apartado :ref:`cerrar-periodos` podemos ir cerrando
períodos o diarios y períodos durante el año para evitar la contabilización de
nuevos datos en periodos o meses concretos.

A parte de esto, **Tryton** provee una opción para realizar dicho cierre para
todos los períodos del año a la vez. Para ello debemos ir al menú
cierres y se nos abrirá un asistente donde solamente tendremos que
indicar el ejercicio fiscal y pulsar en *Cerrar*, una vez realizado esto ya no
se podrán introducir apuntes contables en ningún periodo del ejercicio fiscal.
