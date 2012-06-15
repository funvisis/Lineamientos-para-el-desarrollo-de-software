=============================================
Virtualización para el desarrollo de software
=============================================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>

:Versión: 1.0 23/05/2012


¿Por qué virtualizar?
=====================

La virtualización es el proceso de crear una versión virtual
de algo, bien sea una plataforma de hardware, un sistema operativo,
un dispositivo o sistema de almacenamiento o recursos de red. Básicamente,
el concepto de virtualización gira alrededor de la emulación de entornos
sobre los cuales no es posible trabajar directamente, bien sea por
su indisponibilidad o por no ser práctico hacerlo.

Cabe ahora la pregunta entonces, ¿qué es virtualizar el entorno
de desarrollo? Un entorno de desarrollo virtual, basa su propósito
en independizar los requisitos de un proyecto de software. Se verá más
claro con el siguiente ejemplo: supón que estás desarrollando
un proyecto el cual requiere que use Python 2.6 (estricto) y que a la
vez usa varias bibliotecas Python con una versión específica y que has logrado
instalar todo perfectamente en tu computadora destinada a desarrollo. Seguidamente
su jefe o cliente le solicita trabajar en otro proyecto que necesita Python
2.7 y varias bibliotecas que ya tienes pero en versiones distintas. El resultado,
es que tienes un problema de compatibilidad de las versiones instaladas en
tu computadora y con el indeseable efecto de que ambas aplicaciones no
pueden ser desarrolladas al mismo tiempo sin que ello signifique hacer un
desastre en las bibliotecas instaladas en tu computadora de desarrollo.

Pongamos otro ejemplo: eres asignado a un nuevo proyecto de software y
debes instalar en tu computadora de desarrollo decenas de paquetes, frameworks
y herramientas de desarrollo. Consecuencia: varios días perdidos en la labor.

La virtualización resuelve estos problemas, proveyendo al desarrollador
de herramientas para que este tipo de situaciones desagradables no ocurran.

Virtualización - Nivel Novato
=============================

Existen varias soluciones cuando se requiere virtualizar. La más obvia
es descargar un software de virtualización e instalar un sistema operativo
completo sobre él. Esta opción resulta súper interesante pues permite, con poco
trabajo y conocimiento avanzado, hacer y deshacer sin preocuparse mucho por
lo que pueda suceder con nuestro sistema operativo anfitrión. Sin embargo,
la adopción de esta opción requiere que el desarrollador cuente con una máquina
lo suficientemente poderosa para como para poder correr el sistema operativo
virtualizado, especialmente si está trabajando en varios proyectos de software
a la vez.

Virtualización - Nivel Curtido
==============================

Por otro lado, muchas veces no es necesario realizar una virtualización de
un sistema operativo completo. En lenguajes como Python, Ruby y Perl (no es
casualidad que todos sean interpretados), existe el concepto de sandbox, lo
cual permite al desarrollador tener varios desarrollos "puros" [#]_ sin preocuparse
por los posibles conflictos entre las bibliotecas requeridas por ellos.

.. [#] Con "puros" quiero decir, completamente basados en componentes escritos en ese lenjuage.

Virtualización - Nivel Veterano
===============================

Es posible que para algunos desarrollos, la virtualización mediante sandboxes
no sea suficiente, pues requieren instalaciones más complejas y varias bibliotecas
escritas en múltiples lenguajes. En este caso, lo mejor es pasar al siguiente nivel
de virtualización. 

Basado en la capacidad y poder de cómputo de tu computadora de desarrollo, puedes tomar
dos caminos: debootstrap o vagrant.

debootstrap
-----------

debootstrap permite crear entornos de desarrollo realmente ligeros y con un costo
en recursos realmente bajo. Sin embargo, requiere del desarrollador algunas habilidades
con la cónsola de comandos y varias horas para poner a punto el entorno de desarrollo.

Vagrant
-------

Vagrant permite crear entornos virtuales de desarrollo mediante el uso de boxs de
VirtualBox. Esto permite que, una vez creada una caja, ésta pueda ser redistribuida
al equipo de desarrollo, disminuyendo considerablemente el tiempo de puesta a punto
del entorno de desarrollo. En el otro lado de la balanza, esta opción no es recomendable
para desarrolladores con computadoras con poca capacidad y poder de cómputo.


