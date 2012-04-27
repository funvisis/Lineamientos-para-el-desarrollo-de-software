==========================================================================
Uso de git como sistema de control de versiones para proyectos de software
==========================================================================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>

:Versión: 1.0 24/04/2012

El fundamento de este documento puede ser encontrado en el documento
*¿Cómo desarrollar proyectos de software?*. En este documento, me
reduciré a explicar el uso del git como sistema de control de versiones.

¿Por qué git?
=============

Existen muchos sistemas de control de versiones, los cuales se han
venido desarrollando a lo largo de muchos años, cada uno con mejoras
sobre el anterior. De entre los sistemas más modernos y más populares,
se encuentra git, el cual fue diseñado por Linus Torvald con el fin
de integrarlo en el desarrollo del Kernel de Linux, del cual él es el
"Dictador Benevolente".

Git incorpora múltiples conceptos de forma integral. El primero de ellos
es el concepto de repositorio local/remoto. En muchos sistemas de control
de versiones antiguos, el control de las versiones (valga la redundancia),
era llevado exclusivamente por el servidor (es el caso de Subversion), por
lo que si un programador deseaba llevar un control aparte o no poseía 
conexión con el servidor, no era posible realizar el control de versiones.
En git eso cambia. El control de versiones se lleva primordialmente de forma
local, lo que no implica que no se lleve de forma remota.

Otro aspecto que hace de git una herramienta interesante es el uso de
los *branchs*. Un *branch* es literalmente una bifurcación, lo cual puede
ser una herramienta para el programador que desea implementar una idea
o un nuevo módulo, pero no desea alterar el proyecto original, que bien
pudiera estar en un estado estable. El control de versiones local permite 
que los desarrolladores puedan trabajar en *branchs* propios sin tener 
que colgarlos en el servidor y, por ende, compartirlos con el resto del 
equipo de desarrollo.

Por último, git permite que existan múltiples repositorios remotos, los
cuales pueden ser desde un servidor en Internet o una máquina de un
compañero conectado a través de un cable cruzado.

¿Cómo empezar con git?
======================

Para comenzar a usar git, primero debe instalarse en el sistema. Para
ello:

    $ sudo apt-get install git

Para incializar un repositorio local vacío:

    $ git init

Esto creará un repositorio git vacío en el directorio actual. Para agregar
archivos al repositorio hacer:

    $ git add <archivo>

Finalmente, para hacer *commit*:

    $ git commit -a
    // Escribir mensaje en el editor de texto de escogencia.
    
Esto es básicamente lo que se debe saber para hacer control de versiones de
forma local.

Git remoto
==========

Suponiendo que ya existe el repositorio remoto, bien en una computadora personal
o en un servidor en línea, se puede agregar al control de versiones local como
un "remoto" de la siguiente forma:

    $ git remote add origin <url>

Luego, si se desea subir los cambios realizados en la copia local, basta con:

    $ git push

Obtener los cambios a partir del servidor: ¿pull o fetch?
---------------------------------------------------------

En git existen dos formas de obtener los cambios que se hicieron en el servidor
a tu copia local: pull y fetch. La diferencia radica en que el primero efectúa
la "mezcla" de forma automática en tanto que el segundo no. ¿Qué es lo recomendable
entonces? Si usted es algo inexperto con git, probablemente lo más sencillo sea
hacer pull, sin embargo, eso conlleva el peligro de perder el control sobre la
mezcla. Si usted desea más bien estar al tanto de los cambios realizados en la
copia remota antes de mezclarla con la copia local, es preferible entonces que
realice un fetch. Los pasos para el mismo son los siguientes:

    $ git fetch

Esto traerá los cambios del servidor y lo guardará en el *branch* "origin". Para
ver los cambios, debe:

    $ git diff origin master

El cual le mostrará los cambios en formato diff de Unix. Si lo desea, es posible
configurar la forma de desplegar esta información para que sea más legible para
seres humanos, usando por ejemplo meld.

Una vez vistos los cambios y estando conforme, se puede efectuar:

    $ git merge origin master

El cual intentará mezclar ambos *branchs* sobre "master". Hay varios métodos de
mezcla en git, pero nos interesará saber que no todos funcionan bajo ciertas
condiciones. En tal caso, git nos mostrará cuáles diferencias existen entre ambos
*branchs* y nos pedirá que hagamos manualmente la mezcla. Usualmente, git escribe
mensajes del diff en los mismos archivos que poseen conflicto en el *branch* donde
se quiere tener el resultado.


Creación de *branchs*
=====================

En la sección anterior se vió como mezclar *branchs*, pero aún no sabemos
crearlos. Crear un *branch* en git es muy sencillo:

    $ git branch test

Lo cual creará un branch llamado test que será copia del *branch* actual donde
estemos. ¿Cómo saber en cuál *branch* estamos? Simple:

    $ git branch

Eso desplegará una lista de *branchs* en pantalla y nos indicará con un asterico
el *branch* actual. Finalmente, para saltar al *branch* recién creado:

    $ git checkout test

¡CUIDADO!: cuando cambiamos de *branch*, todos los cambios sobre archivos que no
hayan sido "respaldados" por un commit se eliminarán, y las copias de los archivos
serán actualizadas por las copias del *branch*

Otras operaciones
=================

Un detalle de git es que no siempre es posible hacer cambios en la estructura del
directorio de forma directa. Es necesario hacerlo por el mismo git. Por ejemplo,
si se deseara eliminar el archivo "annoying_code.py", es necesario hacer:

    $ git rm annoying_code.py

De la misma forma, si se deseara mover un archivo de un lugar a otro se debe hacer:

    $ git mv annoying_code.py boring/annoying_code.py

Otros comandos git
==================

   bisect     Busca por búsqueda binaria un cambio que haya introducido un error
   clone      Clona un repositorio a un nuevo directorio
   grep       Imprime líneas que igualen un patrón
   log        Muestra los *logs* de los *commits*
   rebase     Mueve los *commits* locales a los *commits* actualizados del *remote*
   reset      Reinicia el *HEAD* actual a un estado específico
   show       Muestra varios tipos de objetos
   status     Muestra el *status* del árbol de trabajo
   tag        Crea, lista, elimina o verifica una etiqueta firmada con GPG
   --help     Imprime la ayuda











