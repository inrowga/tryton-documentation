============
Mandato SEPA
============

El mandato SEPA (de la terminología inglesa *Single Euro Payments Area*) u orden 
de domiciliación es el medio por el que el deudor autoriza y consiente al 
acreedor a:

 * Iniciar los cobros mediante el cargo en la cuenta indicada por el deudor 
 
 * La entidad del deudor a cargar en su cuenta los adeudos presentados al 
   cobro por la entidad bancaria del acreedor.
   
El mandato debe estar suscrito por el deudor como titular de la cuenta de 
cargo o persona en disposición de poder otorgado por éste, antes de iniciar 
el cobro de los adeudos. El mandato firmado debe quedar almacenado en poder 
del acreedor mientras esté en vigor, durante el periodo de reembolso, así 
como durante los plazos que establezca la Ley para la conservación de 
documentos, una vez cancelado.

Para cualquier duda legal relacionada con el mandato SEPA, en este `link`_ 
encontrarás toda la información oficial. 

Procedimientos para generar un mandato
======================================

Para empezar los pasos y generar la solicitud SEPA al Tercero al que 
pretendamos girar una o más facturas deberemos abrir el |menu_payment_sepa|. 
Escogiendo el tipo entre:

 * Una vez
 
 * Recurrente
 
Aunque este no es un campo realzado como obligatorio, por defecto uno u otro 
tipo esta seleccionado. En cambio el *Tercero*, la *Empresa* y el *Esquema* sí 
son campos obligatorios. Es posible modificar todos estos campos mientras 
tengamos el mandato en formato borrador. Así mismo, cuando pasamos de borrador 
a solicitud, aún podemos modificar el esquema y el tipo, además de añadir el 
*Número de cuenta*, la *Identificación* y la *Fecha de firma*.  

.. view:: account.payment.sepa.mandate_view_form

   Vista formulario del Mandato SEPA

La solicitud no se confirma hasta que no la validamos. Ahora bien, para 
validarla hay que introducir la fecha de firma, la identificación y el número 
de cuenta. Este último significa introducir una única cuenta bancaria 
vinculada al tercero, por el qual si modifica su cuenta deberemos crear un nuevo 
mandato para girarle las facturas, de nuevo. La cuenta necesitará estar 
identificada por los números de *Tipo* IBAN u Otro, además de añadirle una 
*Secuencia*.

Una vez validado el mandato habremos finalizado el proceso. 



.. |menu_payment_sepa| tryref:: 
account.menu_payment_sepa_mandate_form/complete_name
.. |party| field:: company.company/party
.. _link: http://www.sepaesp.es/sepa/es/faqs/elmandato/