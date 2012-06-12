==========================
Cómo hacer commits con git
==========================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>

:Versión: 1.0 16/06/2012


El propósito de este corto documento es servir de guía a
la hora de realizar commits bajo el sistema de control de
versiones git.

¿Cuándo hacer commit?
=====================

La primera pregunta que viene a la cabeza es: ¿cuándo es
el momento apropiado para realizar un commit?

En otros sistemas de control de versiones, hacer commit 
posiblemente implicaba un cambio en el repositorio centralizado.
Sin embargo, en sistemas como git o mercurial, donde el
control de versiones es distribuido (local y centralizado
al mismo tiempo) y existe la posibilidad de hacer bifurcaciones
(branchs), hacer un commit es mucho más simple.

Dicho eso, la respuesta para la pregunta planteada al comienzo
es: cuando sea necesario hacerlo.

¿Qué debe incluir un mensaje de commit?
=======================================

El mensaje de un commit debe contener:

- Un título que no sobrepase las 80 columnas indicando el
  cambio más importante realizado en este commit.
- Las líneas siguientes deben contener el detalle de los
  cambios hechos en el commit.
- Opcionalmente, puedes firmar el commit al final con tu nombre
  o pseudónimo.

