==================================================
¿Cómo desarrollar proyectos de software? - Parte I
==================================================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>

:Versión: 1.0 24/04/2012

Filosofía
=========

"Escribe programas que hagan una cosa, y que la hagan bien" - Doug McIlroy

Los sistemas Unix han sido referente durante mucho tiempo para el
mundo del software libre y es por una sencilla razón: durante mucho
tiempo Unix se ha venido desarrollando y en base a eso, los 
desarrolladores han experimentado innumerables situaciones, las cuales,
sin importar la época en la que desarrollemos, tieden a repetirse. Por
tal motivo, invito al lector de este documento a revisar rápidamente
los *principios filosofales de Unix* [#]_ antes de continuar. Serán de
especial ayuda en el afán de comprender la naturaleza de este documento.

.. [#] http://en.wikipedia.org/wiki/Unix_philosophy

Motivación
==========

Durante el desarrollo del proyecto Sismocaracas (usando el framework web
Django), surgieron entre los desarrolladores varias controversias sobre
cómo debería ser el enfoque a seguir durante el desarrollo. Guíados
sobretodo por la filosofía Unix, se construyó de manera conceptual, un
esquema de los puntos fundamentales en todo desarrollo de software 
profesional:

- Estructura de los proyectos y las aplicaciones
- Estilo de programación
- Control de versiones
- Pruebas
- Seguimiento
- Puesta en producción

Al comenzar cualquier desarrollo de software, las primeras preguntas evidentes
son: "¿Cómo lo voy a hacer? ¿Qué lenguaje usaré? ¿Qué herramientas existen
que resuelvan parte del problema?"; éstas guían el desarrollo y la respuesta
que se escoja a cada una de ellas determinará buena parte del destino del
proyecto de software. Sin embargo, los puntos antes tratados son agnósticos
de éstas respuestas, y no comprometen de ninguna manera la libre escogencia
de las herramientas que el programador desee usar.

Más allá de los detalles de implementación propios del desarrollo, éste debe
contemplar los puntos antes mencionados de forma natural y endógena.

Estructura de los proyectos y las aplicaciones
==============================================

Hacer proyectos complejos a partir de módulos pequeños y simples debe ser
siempre una máxima a la hora de desarrollar. La escogencia de una estructura 
para los proyectos y aplicaciones afectará de forma positiva o negativa este
objetivo. Sin embargo, este punto es bastante abstracto y puede variar de
desarrollo en desarrollo, por tal motivo, se sugiere seguir estas convenciones:

- Si algo es muy grande y complejo, posiblemente pueda ser picado en
  una o varias partes más pequeñas y, de ser posible, independientes.
- De ser posible, plantee soluciones que puedan ser implementadas de
  forma bottom-up, i.e., aplicaciones pequeñas y bien probadas que
  puedan interoperar con otras aplicaciones a través de una interfaz
  clara y simple.
- Reutilice siempre que se pueda, tanto aplicaciones propias como ajenas.
- Si usted creó y refinó su propio estándar, apéguese a él y
  documéntelo apropiadamente.

Estilo de programación
======================

Desde hace muchos años programar no es una actividad solitaria. Aquellos años
de desarrolladores metidos en sótanos y aislados de la sociedad quedó en el
pasado. Hoy en día el desarrollo de software se basa en la colaboración y el
trabajo en equipo. Aún cuando muchos sistemas sigan siendo desarrollados por
equipos de una sola persona, muy probablemente, este software continuará en
operación después de que ésta culmine el trabajo y, eventualmente, se retire.

Por tal motivo, es necesario que todo desarrollo se apegue a reglas simples de
cómo programar. Cada lenguaje ofrece guías de estilo, las cuales deben ser
referencia obligada del desarrollador antes de comenzar el proyecto. Por otro
lado, la filosofía Unix nos otorga de nuevo algunos fragmentos de su sabiduría:

- La claridad es siempre mejor que la elegancia y la genialidad.
- Escribe programas que sean fáciles de inspeccionar y debuggear.

Control de versiones
====================

Mientras que los dos puntos anteriores son más subjetivos y dependientes del
lenguaje o herramienta de desarrollo que estés utilizando, este punto es totalmente
objetivo y no da lugar a dudas: debes llevar control de versiones de tus proyecto
de software.

Pocas cosas son tan imprescindibles para un desarrollador profesional como el
control de versiones, por varios motivos: 

- Facilita el trabajo en equipo.
- Facilita el seguimiento del desarrollo al crear una historia detallada de éste. 
- Estimula la creación de nuevos módulos sin temor a dañar el proyecto original.

Hace algunos años, el control de versiones era un poco más que un respaldo del
proyecto en un lugar seguro, pero con el paso de los años, se ha vuelto una 
herramienta mucho más versátil y que ofrece mucho más que respaldo de código.

Pruebas
=======

"Todo código es culpable, hasta que se demuestre lo contrario" - Anónimo

En el mundo del desarrollo del software, un componente que no se prueba adecuadamente
es incorrecto por diseño. Por tal motivo, es obligación del desarrollador
diseñar y efectuar pruebas intensivas y extensivas a la aplicación que desarrolla.

Para tal fin, existen varios métodos, pero me gustaría poner sobre la mesa dos
métodos fundamentales:

- Pruebas unitarias: pruebas pequeñas realizadas sobre clases y/o funciones
las cuales pretenden comprobar la *correctitud* de las mismas en distintas situaciones.
Este tipo de pruebas dependen mucho de la capacidad del programador en pensar
situaciones típicas y atípicas (casos borde), y no todo el mundo tiene buena
capacidad para ello (incluyéndome), por lo que a veces es necesario el trabajo
conjunto de varios programadores para diseñar un buen conjunto de pruebas.

- Pruebas caja negra: durante el desarrollo, es muy probable que se encuentren
piezas de software en las cuales no es factible realizar pruebas unitarias, como
por ejemplo aquellas que van destinadas a la interacción directa con el usuario.

Una buena medida de la calidad de un software consiste por revisar cuantas pruebas
éste a pasado.


¿Qué sigue?
===========

En la parte dos, se revisarán los aspectos relativos a seguimiento y a puesta en 
producción, que como dice la frase inglesa "*last but not least*", conforman una
parte importante en todo este proceso de desarrollo de software.











