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

Get the sources and put into ``trytond/modules`` with the directory name
*trytond_doc*.

Modify the file *trytond_doc/userdoc/conf.py.template* replacing the variables
substitution for a value. You identify them because appear as'${trytond-conf:X}'
Change the name of the file removing the '.template' ending.

Create symbolic links to the 'doc' directory of the modules you want to include
in the manual inside the 'userdoc' directory and with the name of the module.

Don't forget the 'trytond_doc' because it has the initial file required to
generate documentation.
You also have to create a symlink 'index.rst' in 'userdoc' directory to
'trytond_doc/doc/index.rst' file.

Install the dependencies required for documentation system::

    $ pip install -r userdoc/requirements.txt

Execute Makefile to generate the customized manual inside the 'userdoc'
directory::

    $ cd userdoc
    $ make

To help with this tasks you will found in the 'trytonspain/tryton-buildout'
project in Mercurial (https://bitbucket.org/trytonspain/tryton-buildout) you
will find (almost other utilities):

- a Buildout configuration that include a 'part' to configure userdoc config
  file from template. It create the 'userdoc' directory in the root of
  'customers' directory.
- the 'create-doc-symblinks.sh' script to generate links to modules 'doc'
  directory (using the directory structure proposed in the project)


License
-------

See LICENSE

Copyright
---------

See COPYRIGHT

