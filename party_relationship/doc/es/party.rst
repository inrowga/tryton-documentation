#:inside:party/party:section:crear-un-tercero#

Desde la pestaña relaciones podremos definir con que otros terceros está
relacionado este tercero. Esto es útil para indicar, por ejemplo los contactos
de una misma empresa, o incluso sus empleados. Para crear una relación basta
con indicar el tipo de relación y el tercero relacionado.

.. |relations| field:: party.party/relations


#:inside:party/party:section:configuration#

Tipos de relaciones
-------------------

En el menú tipo de relaciones podemos definir los tipos de relaciones entre
terceros.

Un tipo de relación, puede tener una relación inversa. Una relación inversa
nos define otra relación que se aplica para todos los terceros que tienen
una relación pero en sentido inverso. Por ejemplo, si definimos la relación
"tiene como empleado" cómo relación inversa de "es empleado de" y definimos
que el tercero A es empleado del tercero B, con la relación inversa
automáticamente obtendremos que el el tercero B tiene como empleado al tercero
A.

.. note:: Es importante rellenar ambos casos de la relación inversa. Siguiendo
    el ejemplo anterior deberemos definir cómo inversa de "tiene como empleado"
    la relación "es empleado de", y a la vez la relación "es empleado de" cómo
    inversa de "tiene como empleado". De este modo, se ligaran los dos lados
    de la relación.

