# LINUX PAG 34 LETS BUILD A PLAYGROUND
## SHELL
> Programa que acepta comandos y se los pasa al sistema operativo para que los ejecute

## MANIPULATING FILES AND DIRECTORIES
- cp - copy files and directories
- mv - move/rename files and directories
- mkdir - create directories
- rm - remove files and directories
- ln - create hard and symbolic links

### wildcards
Son caracteres especiales que nos ayudan a especificar grupos de nombres de archivos. Usar wild card

* (*)    matches any characters
* ?       matches any single character
* [characters]  matches any character that is a member of the set characters
* [!characters] matches any character that is not a member of the set characters
* [[:class]]    matches any character that is a member of the specified class

### mkdir - Create Directories
    The mkdir command is used to create directories.

    ejemplo:
        mkdir dir1
        mkdir dir1 dir2 dir3

### cp - Copy files and directories
    The cp command copies files or directories. It can be used two different ways.

### mv - move and rename files
    The mv command performs both file moving and file renaming, depending on how it is used.

### ln - create links
    The ln command is used to create either hard or symbolic links. It is used in one of two ways:

    ln file link

    to create a hard link:

    ln -s item link   

### lectura de lo que muestra el comando ls
-rw-r--r-- 1 v1k1ngg0d v1k1ngg0d 1379 Feb 15 20:27 README.md
drwxr-xr-x 2 v1k1ngg0d v1k1ngg0d 4096 Feb 15 20:27 book

posicion_1: indica el tipo de archivo
	- = archivo regular
	d = directorio
posicion 234 = permisos de acceso
posicion 567 = files's group
posicion 8910 = everyone else
    





