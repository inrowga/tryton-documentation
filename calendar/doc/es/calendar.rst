==========
Calendario
==========

.. inheritref:: calendar/calendar:section:creacion_de_un_calendario

Creación de un calendario
=========================

Para añadir el servicio de calendario a Tryton, proceda de la siguiente forma:

* Abra el menú |menu_calendar_form| i cree un nuevo calendario
* El propietario del calendario puede ser cualquier usuario con una dirección
  de correo electrónico. Si no encuentra ninguno de sus usuarios, compruebe en
  |menu_user_form| si cada usuario tiene establecida una dirección de correo
  electrónico.
* En la pestaña **Seguridad** puede dar permisos de lectura y/o escritura a
  otros usuario Tryton.

.. |menu_calendar_form| tryref:: calendar.menu_calendar_form/complete_name
.. |menu_user_form| tryref:: res.menu_user_form/complete_name

.. inheritref:: calendar/calendar:section:creacion_de_eventos

Creación de eventos
===================

Para crear un evento proceda de la siguiente forma:

* Abra el menú |menu_event_form|
* Cree un nuevo evento
* Rellene los campos |classification|, |calendar|, |transp| y |dtstart|.
* Añada un *Resumen* y una *Descripción*

.. |menu_event_form| tryref:: calendar.menu_event_form/complete_name
.. |classification| field:: calendar.event/classification
.. |calendar| field:: calendar.event/calendar
.. |transp| field:: calendar.event/transp
.. |dtstart| field:: calendar.event/dtstart

