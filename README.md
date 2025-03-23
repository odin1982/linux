# LINUX PAG 53 Redirection
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
    

### creating hard links
Los Hard Links son útiles cuando necesitas múltiples nombres para el mismo archivo sin duplicar datos. Son especialmente usados en sistemas de respaldo o cuando quieres evitar la pérdida de datos accidentalmente.

- vamos a crear un archivo y verificar su inodo
```
$ nano archivo.txt
$ ls -li archivo.txt
```
El inodo es el numero al inicio en este caso 11655
```
11655 -rw-r--r-- 2 v1k1ngg0d v1k1ngg0d 30 Feb 28 23:15 archivo.txt
```
- crearemos un hard link
```
$ ln archivo.txt enlace-duro.txt
```
Ahora lso dos archivos comparten el mismo inodo
```
11655 -rw-r--r-- 2 v1k1ngg0d v1k1ngg0d 30 Feb 28 23:15 archivo.txt
11655 -rw-r--r-- 2 v1k1ngg0d v1k1ngg0d 30 Feb 28 23:15 enlace-duro.txt
```

Si haces un cambio en archivo.txt se vera reflejado en enlace-duro.txt

## WORKING WITH COMMANDS
### creating your own commands with alias
It's possible to put more than one command on a line by separating each command with a semicolon character
```
cd ejercicios-practica/;ls
```

Creating alias:
```
$ alias foo='cd ejercicios-practica/;ls'
```

Remove alias:
```
$ unalias <alias-name>
```

To see all the alias
```
$ alias
```

Cuando termines la sesion de la terminal se borraran los alias

## REDIRECTIONS

● cat - Concatenate files
● sort - Sort lines of text
● uniq - Report or omit repeated lines
● grep - Print lines matching a pattern
● wc - Print newline, word, and byte counts for each file
● head - Output the first part of a file
● tail - Output the last part of a file
● tee - Read from standard input and write to standard output and files

### Redirecting Standard Output (Como guardar salidas de comandos en un archivo) >
Cualquier comando que mande una salida se puede guardar en un archivo con el operador de redireccion >

```
ls -l > reportFiles.txt
```
![Descripción de la imagen](/images/Screenshot_1.png)

El operador agrega contenido al archivo no sobreescribe como el operador >

```
ls -l >> reportFiles.txt
```
![Descripción de la imagen](/images/Screenshot_2.png)

### Redirecting Standard Error
Para guardar un error al ejecutar un comando que produce este error,  se puede hacer de la siguiente forma
```
ls /directorio_no_existente 2> error.txt
```
Al querer mostrar los archivos de un directorio inexistente linux te envia un error, este error se guardara en el archivo error.txt
![Descripción de la imagen](/images/Screenshot_2.png)
