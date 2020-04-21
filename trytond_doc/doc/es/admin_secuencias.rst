.. _admin-secuencias:

===================
Crear una secuencia
===================

Las secuencias son el mecanismo que tiene Tryton para configurar numeraciones
y dárselas a los distintos registros (albaranes, facturas, terceros, etc.)
que vamos a ir creando durante nuestra gestión. Podemos encontrar dos tipos de 
secuencias en Tryton: **estándares** y **estrictas**.

* A las primeras accederemos por medio de las sequecias  y serán las utilizadas
  para la gran mayoría de documentos como ventas, compras o números de albaranes.

* Las estrictas las encontraremos en el menú sequencias estrictas y serán
  utilizadas para aquellos documentos que no permiten saltos de numeración.
  (Como por ejemplo las facturas que según la legislación actual han de estar
  numeradas correlativamente si que haya saltos en la numeración).

Una vez accedemos a cualquiera de los dos tipos de secuencias nos aparecerán un 
listado con todas las secuencias creadas. Para crear una nueva clicaremos en
el icono *Nuevo* y se nos abrirá la vista detallada de secuencia, donde podremos
editar los distintos campos:

.. view:: ir.sequence_view_form

   Captura de pantalla de secuencias
  
Entre los campos editables cabe destacar: 

* Prefijos: A las secuencias podemos añadirles prefijos como el úmero del año, 
  mes o día actual (``%{year}, %{month} o %{day}`` respectivamente) además de
  letras y/o números.
* Sufijos: De la misma forma podemos añadir un sufijo por si queremos un 
  identificador para diferenciar los registros (por ejemplo "V" para las ventas,
  "A" para los albaranes, etc.).
* Tipo: En este campo podemos seleccionar si queremos que las numeraciones se 
  basen en números consecutivos o basado en la hora en la que se crea el registro.
* Relleno del número: Aquí introduciremos el número total de dígitos que debe ocupar un
  número. 
* Cantidad al incrementar: Por medio de este campo es posible indicar que los números 
  no salten de uno en uno sinó que lo hagan de dos en dos, de tres en tres...
    
.. hint:: Es recomendable que la secuencia tenga un relleno del número relativamente 
   grande para que así podamos ordenar por el número de asiento correctamente. De no
   ser así, Tryton podría mostrarnos el documento“10” antes que el “2” ya que ordena
   los números como si se tratara de texto.

