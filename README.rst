trytond-doc
===========

The trytond-doc is the project of generating Users and Administrators manual
auto-generated in base of a list of modules (tipically, the modules installed
in the customer's instance).

It supply the reStructured files in 'doc' directory for each core module
represented by a subdirectory with the same name than documented module.

The 'trytond_doc' directory contains the documentation for tryton base: the
server and the GTK client. It also contains the 'userdoc' directory with the
files to generate the manual dinamically. See the next section to know to do
that.

We hope that this documentation system and manual pages of core modules will be
integrated in Tryton's core after the community review.


Usage
-----

To preapre a Tryton documentation project you should need to install two Sphinx
extensions: **sphinxcontrib-inheritance** and **trydoc**:

    $ pip install sphinxcontrib-inheritance
    $ pip install trydoc

You can use the provided requirements.txt file:

    $ pip install -r requirements.txt

The *trydoc* extensions provide some scripts to prepare and mantain this
project. It is explained in `trydoc package documentation
<http://pythonhosted.org/trydoc/#tryton-documentation-project-provided-scripts>`_.

    $ trydoc-quickstart <lang_code> <project documentation directory>
    $ trydoc-symlinks <lang_code> <path to modules directory> <project documentation directory>
    $ trydoc-symlinks --no-remove <lang_code> <path to trytond-doc project> <project documentation directory>
    $ trydoc-update-modules -c <path to modules.cfg> -t <path to trytond directory> <project documentation directory>

You will find more information in *--help* of each script.

After that you can generate the manual using *make* command:

    $ cd <project documentation directory>
    $ make html

License
-------

See LICENSE

Copyright
---------

See COPYRIGHT

