==========
Comisiones
==========

La comisión es la cantidad que se cobra por realizar transacciones comerciales
que corresponden a un porcentaje o un importe fijo sobre el importe de la operación.

Las comisiones se calculan sobre las facturas.

.. inheritref:: commission/commission:section:planes

Planes
======

En nuestro sistema deberemos definir que planes se aplicarán para la generación
de comisiones.

Un plan irá relacionado con un producto y el método de comisión.

El método de comisión es el estado de la factura en que se creará la comisión:

* Al confirmar
* Al pagar

Los planes irán relacionados con varias líneas. Cada línea la podemos relacionar
con un producto. En el caso que la comisión sea sobre este producto, se calculará
la comisión sobre este producto.

La formula de las líneas de los planes son cálculos matemáticos. Por ejemplo, si la
comisión es de un 10% del total, el operador será:

.. code::

    amount*0.1

.. inheritref:: commission/commission:section:agentes

Agentes
=======

Los agentes son los comerciales de nuestra empresa, sean empleados de la propia empresa
o personal externo (autónomos).

Cada agente irá relacionado con un "plan de comisión". Según el plan de comisión
se le calculará el tipo de comisión que ganará el agente.

El tipo de agente, "agente de" o "principal" nos permite especificar la cuenta del agente que
se usará.

Si el agente es "Agente de" se usará la cuenta "Cuenta a pagar" del tercero/agente.
Si el agente es "Principal" se usará la cuenta "Cuenta a cobrar" del tercero/agente. 

.. inheritref:: commission/commission:section:creacion_comisiones

Creación de comisiones
======================

Las comisiones se crean automáticamente según el tipo de plan que hayamos definido (al confirmar
o al pagar).

.. inheritref:: commission/commission:section:relacionar_facturas_con_agentes

Relacionar facturas con agentes
===============================

A la factura disponemos del campo "Agente de comisiones" que nos permite relacionar
la factura con el agente.

En el caso que la factura esté relacionado con un agente, en el momento de confirmar o pagar
la factura (según el plan) nos genera la comisión relacionado con el agente.

En el caso que la factura provenga de una venta, por ejemplo, en una factura disponemos
de diferentes líneas que pueden que el origen sean de diferentes ventas, y por tanto,
de diferentes agentes. En el caso que las líneas de la factura tengan un agente,
tendrá preferencia este agente respecto el agente global de la factura o de si no disponemos de agente,
y las comisiones que se generarán serán respecto a la línea de la factura.

Si la factura es de cliente, nos genera comisiones en positivo. Si la factura es de cliente y devolución,
nos genera las comisiones en negativo.

.. inheritref:: commission/commission:section:facturar_comisiones

Facturar las comisiones
=======================

Des del menú de Comisiones disponemos de un asistente que nos permite generar facturas a partir
de un rango de fechas.

En este asistente le podemos especificar el tipo de factura:

* Entrante. Nos generará facturas de los agentes que el tipo sea "principal".
* Saliente. Nos generará facturas de los agentes que el tipo sea "agente de".
* Ambos. Nos generará facturas de los agentes que sean "principal" y "agente de".

Para generar las facturas de la comisión es importante que los agentes dispongan un
"plazo de pago" tanto de cliente como proveedor por defecto antes de ejecutar el asistente.
En el caso que el agente no disponga de esta información, una mensaje de alerta nos avisará que no
puede generar la factura, pues este campo es requerido en la factura.

.. inheritref:: commission/commission:section:cancelar_facturas

Cancelar facturas relacionadas con comisiones
=============================================

En el caso que se cancele una factura que las líneas estén relacionadas con comisiones
ya facturadas, estas comisiones pasarán a estado "cancelado".
