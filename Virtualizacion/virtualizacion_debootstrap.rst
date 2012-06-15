==============================
Virtualización con debootstrap
==============================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>

:Versión: 1.0 10/05/2012

¿Qué es debootstrap?
====================

Debootstrap es una herramienta que permite instalar un sistema base
Debian en un subdirectorio de otro sistema ya instalado.

Contrario a la virtualización vía VirtualBox, debootstrap no compromete
muchos recursos del sistema, por lo que puede ser usado en computadoras
con pocos recursos.

Debootstrap usa chroot para poder hacer posible la virtualización, por
lo que no es una virtualización completa, sino más bien una virtualización
a nivel de directorios y "pahts" tal y como lo hace virtualenv, con la
ventaja que chroot lo hace a nivel de sistema y no solamente reducido
al intérprete Python.

Una guía simple para instalar un sistema base vía debootstrap se puede
encontrar en https://help.ubuntu.com/community/DebootstrapChroot.

Sí vas a usar debootstrap, debes tener en cuenta:

- Instalarás un sistema base con los requisitos mínimos, i.e. no
  tendrás programas que usualmente das por sentado, incluso vim.
- Si tienes que instalar bibliotecas de con alcance de sistema, es probable que
  debas instalar algunas otras cosas, pues probablemente el proveedor
  de la biblioteca asume que ya tienes un conjunto básico de programas
  y/o bibliotecas instalado.
- Es recomendable instalar sistemas base que sean estables, como por
  ejemplo, algún Ubuntu LTS o un sistema Debian.
- Todo será por cónsola (por si acaso no eres amante de esta maravillosa
  herramienta).


