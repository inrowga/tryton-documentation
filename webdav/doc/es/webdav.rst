======
Webdav
======

En el menú |menu_webdav| se configura que directorios serán accesibles.
Por ejemplo si se desea poder acceder a los terceros y ver y gestionar su adjuntos,
se crea un directorio llamado "terceros", y relacionado con el modelo "Tercero".

Ahora es el momento de configurar tu sistema operativo que trabaje con Webdav.
Por ejemplo en Linux se puede hacer desde el programa Navegador
de ficheros que lleva por defecto (Nautilus).

Para conectarnos con el Navegador de ficheros, se abre con el menú Fichero/Conectar
al servidor ... y se introducen los datos del servidor webdav:

* **Servidor:** IP o dominio del servidor
* **Puerto:** 8001 (por defecto)
* **Tipo:** WebDAV (HTTP)
* **Carpeta:** /mibasedatos (el nombre de la base de datos)
* **Usuario:** Usuario del ERP
* **Contraseña:** Contraseña del ERP

Una vez conectados, podemos acceder en la carpeta que hemos creado, en este 
ejemplo, "terceros". Los podemos gestionar como cualquier fichero, abrir, copiar,
pegar, eliminar, etc.

.. |menu_webdav| tryref:: webdav.menu_webdav/complete_name
