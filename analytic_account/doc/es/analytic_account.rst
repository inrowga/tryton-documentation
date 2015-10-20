#:after:account/account:section:otras_tareas_contables#

.. inheritref:: analytic_account/analytic_account:section:planes

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
encontramos en la entrada de menú *Contabilidad/ Configuración/ Contabilidad 
analítica/ Cuentas analíticas/ Cuentas analíticas*.

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