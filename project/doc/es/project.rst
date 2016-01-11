=========
Proyectos
=========

.. inheritref:: project/project:section:proyectos

Proyectos
=========

La gestión de **proyectos** le permite la gestión de estos y de sus tareas.

* **Proyectos** podrá dar de alta los proyectos que está
  trabajando su empresa.
* **Tareas** podrá dar de alta los tareas asociados a proyectos
  o a otras tareas (árbol).

El módulo de proyectos contiene como base el módulo `partes de trabajo
<../timesheet/index.html>`_ y todas las funcionalidades de los partes de trabajo
se ven reflejados en proyectos y tareas de proyecto.

Toda la gestión de proyectos accederemos en el menú principal a: |menu_projects|.

.. |menu_projects| tryref::  project.menu_project/complete_name

.. inheritref:: project/project:section:proyecto

Proyecto
========

Para crear o listar los proyectos accederemos a |menu_project|.

.. |menu_project| tryref:: project.menu_project_form/complete_name

Una proyecto está compuesta principalmente por **tareas** y **parte de trabajo**.

Las *tareas* le permiten en un proyecto especificar las acciones a realizar, mientras
que el *parte de trabajo* le permitirá anotar el tiempo empleado en el proyecto.

* |party|: El cliente relacionado este proyecto.
* |party_address|: La dirección de contacto de este proyecto.
* |children|: Un proyecto lo podemos relacionar parte de otro proyecto.
* |sequence|: Orden de los proyectos a mostrar.
* |work|: Trabajos realizados en este proyecto.

Los campos |party| y |party_address| son campos opcionales, ya que podemos crear
proyectos que no esten relacionados a ningún cliente (internos, por ejemplo).

.. inheritref:: project/project:paragraph:en_proyectos_disponemos_de_campos

En proyectos disponemos de campos que nos informarán sobre el tiempo empleado en
el proyecto:

* |effort_duration|: Tiempo total empleado en este trabajo.
* |total_effort|: El tiempo total estimado para este trabajo y subtrabajos.

.. |party| field:: project.work/party
.. |party_address| field:: project.work/party_address
.. |children| field:: project.work/children
.. |sequence| field:: project.work/sequence
.. |work| field:: project.work/work
.. |effort_duration| field:: project.work/effort_duration
.. |total_effort| field:: project.work/total_effort

.. inheritref:: project/project:section:tarea

Tarea
=====

Una tarea es muy similar a un proyecto y también podemos anotar tiempos en las
tareas.

.. inheritref:: project/project:paragraph:para_la_gestion_de_tareas

Para la gestión de tareas accederemos en el menú |menu_task|.

.. |menu_task| tryref:: project.menu_task_form/complete_name

.. inheritref:: project/project:section:estados

Estados
=======

Los estados de un proyecto o tarea son:

* Abierta a Realizada
* Realizada a Abierta
