#:before:account/account:section:consulta_asientos#

Definir la obligatoriedad de la analítica de las cuentas contables
==================================================================

Toda cuenta contable debe tener definido si la analítica es **obligatoria**, 
**prohibida** u **opcional**. Esta configuración es por jerarquía, pudiendo 
indicar que los apuntes contables de una cuenta deben tener obligatoriamente 
líneas analíticas para una jerarquía pero no pueden tenerlos para otra. 
Normalmente, la analítica debería ser obligatoria para las cuentas 6 y 7, y 
prohibida en el resto. Pero tal vez queremos tener una jerarquía para controlar 
el flujo de caja; de manera que configuraremos, para esta segunda jerarquía, 
que las cuentas 57 tengan la analítica requerida (esta es una explicación 
simplificada de cómo deberíamos configurar este caso).

La comprobación de analítica prohibida se comprueba cuando se crea un apunte 
contable (y cada vez que se modifica), la obligatoriedad se comprueba cuando el 
apunte se contabiliza. 

.. Warning:: para poder operar sin errores, debemos tener todas las cuentas 
   configuradas para todas las jerarquías. En caso contrario, nos saldrá un 
   error cuando intentemos crear un apunte en una cuenta no configurada. 

Configurar desde cuentas analíticas
-----------------------------------

Este es el procedimiento recomendado, debido a que, es el más rápido para 
configurar un gran número de cuentas contables (cuando configuramos la analítica 
por primera vez). Ahora bien, el plan contable debe estar creado. 

.. Imagen de la pestaña en comentada con el formulario de cuentas analíticas

Debemos ir al formulario de la cuenta analítica que sea raíz de cada jerarquía, 
a la pestaña **Configuración analítica en cuentas**. El campo **Cuentas
pendientes** nos muestra, de forma dinámica, las cuentas que aún no hemos 
añadido en ninguno de los otros tres campos. El objetivo es dejar este campo 
vacío. El sistema no nos dejará añadir una misma cuenta a más de un campo. Si 
nos equivocamos, deberemos quitarlo primero del grupo que lo hayamos añadido 
erróneamente y luego añadirlo al correcto (no hace falta guardar el registro 
por cada cambio). 

Configurar des de cuentas contables
-----------------------------------

Este procedimiento lo usaremos cuando tengamos que configurar una cuenta 
contable específica porque este acabada de crear, porque nos demos cuenta que 
está mal configurada, etc. Aunque también lo podríamos hacer con el 
procedimiento anterior. La única condición para no hacer trabajo en vano es que 
debemos tener todas las jerarquías analíticas ya creadas.

.. Imagen pestaña configuración analítica del formulario de cuenta contable

En el formulario de cuenta contable tenemos la pestaña **Configuración 
analítica** que es exactamente igual que la configuración de las cuentas 
analíticas, y se comporta de la misma forma. La única diferencia es que sólo nos 
aparecerán las cuentas analíticas raíz. 