======================
Unidad de medida (UdM)
======================

La unidad de medida está definida por el nombre, un símbolo, la categoría de
unidad de medida, un coeficiente multiplicador, un factor, la precisión del
redondeo y los decimales a mostrar y un campo de tipo booleano que permite
desactivar el registro sin borrarlo.

Factor
======

El campo **factor** en las unidades de medida define la relación existente
entre dicha unidad de medida y la unidad de medida considerada *base*. Este
concepto se entenderá mejor con un ejemplo:

  La unidad de medida de longitud es el metro. Sin embargo, normalmente se
  utilizan también múltiplos y submúltiplos de dicha unidad cuando no es cómodo
  trabajar con ella. Se definen de esta forma los decámetros, hectómetros o
  kilómetros como múltiplos del metro, o los decímetros, centímetros o
  milímetros como sus submúltiplos. Pues bien, el campo **factor** define la
  relación que guarda estos múltiplos/submúltiplos con su unidad fundamental.
  De esta forma, el centímetro tendría un valor de 0,01 metros, o el kilómetro
  tendría un valor de 1000 metros.

Ratio
=====

El campo **ratio** define la relación contraria (inversa) a la definida en el
campo **factor**, es decir, si el valor del campo **factor** es 1000, el valor
del campo **ratio** deberá ser 0,001.

=============================
Categoría de unidad de medida
=============================

Una categoría de unidad de medida define simplemente un nombre que se utilizará
más adelante para añadir una categoría a las unidades de medida.
