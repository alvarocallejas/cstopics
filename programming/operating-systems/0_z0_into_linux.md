---
layout: default
title: Introduction to Linux
permalink: /programming/operating-systems/0_z0_into_linux
---

# Introduction to Linux

Before developing this guide, install Linux in your computer (Ubuntu 18.04 or 16.04 are recommended).

## What is GNU/LINUX?

GNU/Linux is an operating system, as Microsoft Windows or macOS, with the main difference that it is open, free and build by a community of contributing programmers and users.

Likewise, as in other operating systems, GNU/Linux is divided in two main sections:

**Kernel** performs direct control over hardware, and abstracts it for the high level applications.
In addition, it manages the resources, in order to guarantee that running programs can access the hardware.

<p align="justify">
**Applications** of the OS allow the user to use the computer in a easy way, without having to understand the internal processes that are taking place inside the processor. This set of applications includes the Graphical User Interface (GUI), the file manager, text editors, etc. The majority of the programs developed for this operating system was build by the [GNU](https://www.gnu.org/home.en.html) project.
</p>

## Linux Distributions

A distribution is a precompiled version of Linux, that includes a set of packages and needed programs to allow the end user to use it in a easy way. Throughout Linux history, there have been tree main distriutions: Debian, Slackware y Red Hat,

Una distribución es una versión precompilada de Linux, en conjunto con paquetes y programas necesarios para permitir el uso de ésto por el usuario final. A lo largo de la historia de Linux han existido tres grandes distribuciones, Debian, Slackware y Red Hat, cada una de las cuales, a su vez, ha desencadenado el desarrollo de distribuciones basadas en ellas. En este link se encuentra esquematizada la jerarquía de la mayoría de distribuciones conocidas de Linux.

El desarrollo de éste curso se llevará a cabo bajo Ubuntu (se recomienda la versión 16.04.3 LTS), una distribución libre de GNU/Linux basada en Debian. Sin embargo, la mayoría de las herramientas y procesos que se realicen, funcionarán de manera correcta en cualquier distribución basada en Debian.

## Sistema de Archivos y Árbol de Directorios

El sistema de archivos manejado por Linux maneja una organización diferente a la acostumbrada en sistemas basados en Windows, en dónde las carpetas más altas en la jerarquía corresponden a las unidades de almacenamiento (C:\, D:\, etc.). En Linux todos los archivos están contenidos en un directorio denominado raíz, y representado por el símbolo "/".

Las unidades o particiones realizadas en las unidades de almacenamiento son "montadas" en directorios, y se acceden a través del sistema de archivos. A continuación se presenta de forma gráfica la jerarquía de directorios, y una breve descripción.

{% include code/programming/os/0_file_system.md %}

Algunos directorios tienen alias para abreviar su escritura, a continuación se presentan algunos (no incluyen las comillas):
* '~' /home/pepito (o el usuario actual).
* '.' directorio actual
* '..' directorio superior

## TERMINAL Y COMANDOS BÁSICOS

La terminal, consola o línea de comandos de Linux es una ventana que permite ingresar comandos del sistema operativo. A través de esta herramienta se pueden realizar tareas que la interfaz gráfica no permite, o que implica una dificultad mayor. En la mayoría de los casos, éstos comandos entregan resultados en la misma terminal.
La terminal se puede abrir en algunas distribuciones de Linux (incluida Ubunbu), con la combinación de teclas ctrl+alt+T. Cuando se inicia una terminal desde la interfaz gráfica de Ubuntu, el directorio de trabajo por defecto es el home del usuario actual.

El prompt corresponde a el conjunto de caracteres que aparecen al inicio de cada línea de la consola, a la espera de ingresar un comando.En el caso de ubuntu, el prompt tiene el siguiente formato:

* nombreDelUsuaio@nombreDeLaMáquina:directorioActual$

Con el fin de simplificar, en los siguientes ejemplos el prompt será abreviado con el símbolo '$'.

Adicionalmente, se pueden adicional comentarios a los comandos ingresados por consola, a través del carácter '#'. Todos los caracteres escritos después de éste símbolo serán descartados por la terminal.

A continuación, se presentan algunos comandos básicos de Linux, en forma de tutorial, así que pueden ser ejecutados en el orden correspondiente para obtener los resultados finales. En el ejemplo, el usuario se llama 'rocio'. (las líneas que únicamente contienen comentarios no necesitan ser ingresadas, las que comienzan con '$' son los comandos a ejecutar (sin el '$'), y las demás son la salida que debe entregar la terminal).

{% include code/programming/os/0_basic_commands.md %}

## COMANDOS DEL TECLADO

A continuación, algunos comandos útiles del teclado para la terminal de Linux:

* ctrl+alt+T: Abrir la terminal.
* ctrl+C: Cancelar el proceso actual.
* ctrl+D: Cerrar sesión actual.

## PROPIEDADES Y PERMISOS DE ARCHIVOS

Al ingresar el comando 'ls -l' para observar el contenido de un directorio en detalle, se obtiene el siguiente resultado:

{% include code/programming/os/0_file_properties.md %}

La primera línea de salida presenta la cantidad de bloque de 1KB utilizados por el directorio, su significado exacto se sale del objetivo de éste tutorial.

A continuación, existe una línea por cada archivo o directorio contenido, cada columna tiene un significado:

* El primer carácter refleja si corresponde a un archivo regular '-', un directorio 'd', entre otros.
* Los siguientes 9 caracteres especifican los permisos del archivo, en grupos de 3. La letra 'r' indica permiso de lectura, 'w' de escritura y 'x' de ejecución y siempre están en dicho orden (los caracteres 'r--' indicarían sólo lectura, y 'rwx' los tres permisos). El primer grupo corresponde a los permisos del propietario del archivo, el siguiente al grupo del propietario, y el último a todos los usuarios.
* El siguiente número indica la cantidad de enlaces del directorio.
* Los siguientes dos campos presentan el nombre del usuario dueño del archivo, y el grupo al que pertenece dicho usuario.
* El siguiente número indica el espacio ocupado por el archivo o directorio en bytes. (Para observar en KB, MB, GB, etc, cambiar el '-l' por '-lh').
* A continuación se presenta la fecha y la hora de la última modificación realizada.
* Por último está el nombre del archivo o directorio.
* Para cambiar los permisos de un archivo, se utiliza el comando 'chmod', el cual se discutirá en la sección 'Scripts de Bash'.

## COMODINES

El comodín más utilizado en Linux es el carácter asterisco ' * ', y se puede usar de las siguientes maneras:

{% include code/programming/os/0_wildcards.md %}

## EDITORES DE TEXTO

A pesar de que el comando 'echo' puede ser utilizado para crear archivos de texto, es más conveniente escribirlos con la ayuda de un editor de texto. Uno de los editores más simples y comunes para terminal se llama 'nano', y está disponible en gran cantidad de distribuciones de Linux (incluida Ubuntu). Para crear un nuevo archivo, se puede ejecutar de la siguiente manera (el archivo puede tener cualquier extensión, no debe ser '.txt' necesariamente):

``` sh
$ cd ~/linuxTutorial
$ nano textFile.txt
```

La terminal cambiará, mostrando el software 'nano'. Se puede escribir normalmente, y el contenido aparecerá en la parte superior. En la parte inferior aparecen los comandos del teclado disponibles, donde el símbolo '^' significa la tecla ctrl.

<div style="text-align:center">
  <img src ="/cstopics/assets/img/programming/os/0_nano_editor.png" />
  <div style="font-size:70%">Nano Editor</div>
</div>

Al terminar de ingresar el texto deseado, se presiona ctrl+O para guardar. Pedirá confirmar el nombre (aquí se podría cambiarlo), se presiona enter y ctrl+X para salir. Se puede confirmar el contenido del archivo:

``` sh
$ cat textFile.txt
Hola mundo desde nano.

Universidad Santo Tomás
```

Para mayor comodidad, existen otros editores de texto que funcionan bajo la interfaz gráfica, como pueden ser: gedit (incluído en Ubuntu), kate, sublime text o atom.

## SUDO

El comando 'sudo' otorga permisos de administrador o superusuario a otro comando, por lo cual, solicitará la contraseña al momento de ejecutarse. Éste comando permite acceder, modificar, o incluso borrar cualquier archivo del sistema, incluyendo los pertenecientes al sistema operativo, por dicha razón, debe ser utilizado con precaución. En la siguiente sección se encuentra un ejemplo del uso de éste comando.

## SCRIPTS DE BASH

Con el fin de automatizar algunos procesos, es posible crear scripts de comandos de Linux, para luego ser ejecutados secuencialmente en un solo comando. Cree un archivo en la carpeta 'linuxTutorial' con el siguiente contenido:

{% include code/programming/os/0_bash_script.md %}

La primera línea indica la ubicación del intérprete que va a ejecutar el script, en éste caso, el programa 'bash' es el encargado. Cuando se guarde el archivo, ésta va a tener los siguientes permisos 'rw-rw-r--', es necesario agregar el permiso de ejecución, por lo menos al usuario dueño, para poder lanzar el script. Los permisos se pueden ver como tres dígitos en sistema octal, y cada bit en 1 indica que el permiso está activo, es decir, nuestro archivo tiene permisos 664, y queremos convertirlo a 764. Ésto se realiza a partir del comando 'chmod', como se observa a continuación:

``` sh
sudo chmod 764 testScript.sh # Solicitará la contraseña
```

Se pueden comprobar los permisos con el comando 'ls -l'. El script se ejecuta se la siguiente manera:

``` sh
$ ./testScript.sh

Universidad Pedagógica y Tecnológica de Colombia
Tutorial de Linux

Creando carpets
Creado archivos

Fin
```

Las impresiones por pantalla correspondientes a los comandos 'echo' se realizaron de forma correcta, y se puede explorar el directorio para comprobar que se crearon las carpetas y los archivos correspondientes.

## GESTOR DE PAQUETES DE UBUNTU

La forma más común de instalar nuevo software en Ubuntu es através del gestor de paquetes 'apt'. Para comprobar su funcionamiento, se va a instalar un software llamado 'tree', el cual permite ver el contenido de un directorio, de forma gráfica y jerárquica. Se ejecuta el siguiente comando (se necesita conexión a internet):

``` sh
$  sudo apt-get install tree
```

Desde el momento en que la instalación termina, se puede hacer uso del nuevo software:

``` sh
$ cd ~/linuxTutorial/
$ tree
.
├── folder101
│   └── file.txt
├── folder102
│   └── file.txt
├── folder103
│   └── file.txt
├── folder104
│   └── file.txt
└── testScript.sh

4 directories, 5 files
```

## VARIABLES DE ENTORNO Y PATH

Las variables de entorno son nombres asociados a cadenas de caracteres, los cuales pueden ser usados en comandos de consola o scripts. La forma original de crear variables de entorno es la siguiente:

``` sh
$ export VAR1='SANTOTO'
```

Sin embargo, en distribuciones más recientes, como Ubuntu, se puede omitir la palabra 'export' e incluso las comillas:

``` sh
$ VAR1='SANTOTO'
$ VAR1=SANTOTO
```

El valor de una variable de entorno puede ser visualizado con el comando 'echo', realizando el llamado con el carácter '$':

``` sh
$ echo $VAR1
SANTOTO
```

Una variable de entorno puede ser utilizada en cualquier comando de consola, por ejemplo, el siguiente comando creará una carpeta con el nombre 'folder_SANTOTO_01':

``` sh
$ mkdir folder_${VAR1}_01
```

Ésta variable es visible únicamente durante la sesión de la terminal actual, es decir, al cerrar y abrir la terminal de nuevo, ya no estará disponible. Existen algunas variables de entorno predefinidas en el sistema:

* HOME: directorio personal del usuario actual.
* HOSTNAME: nombre de la máquina.
* USER: nombre del usuario actual.
* Adicionalmente, se pueden conocer todas las variables de entorno disponibles con el comando 'env'.

Existe una variable de entorno llamada 'PATH', la cual tiene una tarea específica: establecer los directorios (separados por dos puntos ':') dónde el sistema operativo busca los comandos que se ejecuta desde consola, ésto quiere decir que todos los comandos vistos anteriormente (cp, mkdir, mv, etc.) son realmente programas que están en una de las carpetas descritas en 'PATH'.

Si se quisiera que el script 'testScript.sh', creado en secciones anteriores, se pudiera ejecutar desde cualquier directorio (sin tener que escribir './testScript.sh' o '/home/rocio/tutorialLinux/testScript.sh'), basta con agregar el directorio que lo contiene al path de alguna de las siguientes maneras:

``` sh
$ cd ~/tutorialLinux
$ export PATH=$PATH:/home/camilo/linuxTutorial # Agrega explícitamente el directorio al PATH
$ export PATH=$PATH:$(pwd) # El carácter '$' junto con los paréntesis evalúa el comando 'pwd', y reemplaza su resultado en el comando principal.
```

Luego de ésto, se comprueba el funcionamiento ejecutando el script desde otra carpeta:

``` sh
$ cd ..
$ mkdir linuxTutorial2/
$ ls
$ testScript.sh

Universidad Pedagógica y Tecnológica de Colombia
Tutorial de Linux

Creando carpets
Creado archivos

Fin

$ ls
folder101  folder102  folder103  folder104
```

Es importante notar que, debido a que el script crea las carpetas y los archivos a partir de directorios relativos, éstos son creados en la carpeta 'linuxTutorial2' y no en 'linuxTutorial'.

Sin embargo, si se sale de la terminal o se apaga el equipo, ya no se podrá ejecutar el script desde cualquier carpeta, ya que la variable 'PATH' volverá a su valor por defecto. Ésto se puede solucionar de varias formas, una de las más comunes es agregar la definición de la variable PATH (de forma explícita) al final del archivo '.bashrc', ubicado en el home del usuario.

<div style="background-color:rgb(255, 99, 71); color:rgb(255,255,255); padding: 30px;">
El archivo <i>'.bashrc'</i> es un archivo protegido del sistema y oculto (todos los archivos y directorios que empiezan por punto '.' son ocultos en Linux). En escencia es un script que se ejecuta cada vez que se abre una terminal nueva. Se puede editar con el comando 'sudo nano ~/.bashrc', sin embargo, se debe ser muy cuidadoso, ya que cualquier daño ocasionado a dicho archivo podría dejar inservible la terminal de Linux.
</div>

## ENLACES SIMBÓLICOS

Un enlace simbólico es una etiqueta o un nuevo nombre asociado a un archivo existente. Ésta etiqueta no contiene los datos del archivo, sino que apunta al sistema de archivos donde están contenidos los datos.

Un enlace simbólico se crea de la siguiente manera:

``` sh
$ ln -s archivo.txt nuevo_nombre.txt
```

Aparecerá como un archivo más en el directorio, y cualquier cambio, tanto a 'archivo.txt' como a 'nuevo_nombre.txt' será reflejado a los mismos datos. A un enlace se pueden aplicar todos los comandos básicos (mv, cp, rm, etc.), sin embargo, si el archivo original es eliminado o movido, el enlace dejará de funcionar o se romperá.

## Usuarios

...

## SSH

...

Fuentes:

<https://www.debian.org/releases/stable/armel/ch01s02.html.es>

<https://www.gnu.org/home.es.html>

<http://swift.siphos.be/linux_sea/whatislinux.html#idm3548300592288>

<https://www.tldp.org/LDP/intro-linux/html/sect_03_01.html>

<https://www.linux.com/learn/understanding-linux-file-permissions>

<https://hipertextual.com/archivo/2014/07/enlaces-fisicos-y-simbolicos-linux/>
