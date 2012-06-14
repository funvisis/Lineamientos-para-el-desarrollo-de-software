===================================================
¿Cómo desarrollar proyectos de software? - Parte II
===================================================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>

:Versión: 1.0 31/05/2012


En la primera parte de este escrito, se describieron varios puntos
importantes en el desarrollo de software, lo cuales son:

- Estructura de los proyectos y las aplicaciones
- Estilo de programación
- Control de versiones
- Pruebas

Todos estos aspectos están íntimamente ligados con el desarrollador en
su día a día: son todas herramientas de uso cotidiano en cualquier
desarrollo.

En esta parte se dedicará un poco a revisar los aspectos fundamentales
del seguimiento y la puesta en producción. Puede el lector preguntarse,
"¿por qué existen dos partes para describir algo que está inmerso en el
mismo proceso?". La respuesta de esto radica precisamente en la dimensión
temporal donde habitan los aspectos que se tratarán en esta parte.

¿Qué quiere decir dimensión temporal? Es muy simple: los sistemas de seguimiento
y puesta en producción son herramientas que no necesariamente son usados
a diario por el desarrollador.

A continuación, se describirá en que consiste cada aspecto y qué beneficios
aporta al ciclo de desarrollo.

Seguimiento
===========


Puesta en producción
====================

Si eres un desarrollador, lo más probable es que uses entornos minimalistas de
desarrollo y configuraciones de prueba para el software que en el cual estás
trabajando. Sin embargo, la realidad suele ser distinta cuando el desarrollo
en el cual trabajas debe pasar a producción, es decir, en contacto directo con
los usuarios, especialmente cuando desarrollas componentes o sistemas para ser
usados por cientos, miles o millones de usuarios cada día. 

Si eres desarrollador web, muy probablemente conocerás muy bien la diferencia
entre los entornos de desarrollo, prueba (si los hubiese) y producción, y de
la dificultad de hacer que lo que hiciste en tu computadora personal funcione
en un servidor de producción. O quizás no... todo depende de la dimensión de tu
trabajo y la cantidad de herramientas externas que uses para que éste funcione.

Sabiendo de antemano este tipo de complicaciones, existen innumerables herramientas
que "facilitan" esta tarea y que permiten que el paso de desarrollo/prueba a
producción sea más sencillo. Nótese que "facilitar" está entre comillas, pues
no necesariamente estas herramientas son de fácil uso al comienzo.

El concepto fundamental detrás de todo esto es el aprovisionamiento. Éste consiste
en indicar, mediante algún script o lenguaje de marcado, cuales son los requisitos
para que una pieza de software en particular funcione.

Por otro lado, existe otra posibilidad que, como efecto colateral beneficioso, proveen
estos "aprovisionadores": la posibilidad de crear ambientes virtuales de desarrollo
distribuibles. Esto significa que para alguien que está entrando nuevo en el equipo
de desarrollo, es bastante fácil que se ponga al tanto de las bibliotecas, herramientas
y demás adminículos que son necesarios para desarrollar.

Notas finales - Modularidad e integración
=========================================

Como ya se mencionó en la primera parte, la filosofía de este documento está
fuertemente ligada a la filosofía Unix. Por tal motivo, las notas finales están
dedicadas dos recomendaciones que se deberían seguir al momento de desarrollar:

- Desarrollo modular: de ser posible, un sistema debe ser picado en partes pequeñas,
  tan pequeñas como sea posible.
- Integración: cuando un proyecto amerite la integración de varios módulos, debe
  existir una documentación apropiada al respecto que indique claramente cuáles
  módulos deben integrarse.



