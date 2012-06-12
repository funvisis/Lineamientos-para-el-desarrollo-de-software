===================
Aplicaciones Django
===================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>
:Versión: 1.0 15/05/2012

¿Qué es una aplicación Django?
==============================

En su forma más pura, una aplicación Django es una pieza
de software que consta de:

  - models.py: un archivo donde se especifican las clases
    que estarán directamente relacionadas con tablas en la
    base de datos mediante el ORM de Django.
  - views.py: un archivo que contiene clases y funciones
    dedicadas a la lógica de la aplicación. Puesto que Django
    es un framework MTV (Model-Template-View), las vistas
    equivalen a al controlador en el modelo MVC.
  - urls.py: relaciona las solicitudes de los clientes, hechas
    mediante urls, con funciones y clases.

Sin embargo, para que una aplicación Django sea efectivamente
una aplicación, sólo requiere de la existencia de modelos.

La diferencia entre un proyecto y una aplicación Django
radica en que un proyecto es una colección de aplicaciones.

Alcance de una aplicación Django
================================

Siguiendo los lineamientos propuestos en "Filosofía", una
aplicación Django debe procurar ser reducida en su funcionalidad,
y con reducida no me refiero a mal hecha o deficiente, sino más
bien pequeña y con una funcionalidad puntual (ver "Layout base"
en documento.

En ese sentido, es importante recordar que un Proyecto Django
es una colección de aplicaciones, por lo que resulta bastante
fácil integrar una aplicación sencilla a cualquier proyecto, en
tanto que integrar una aplicación compleja requiere más trabajo.

Quedará en potestad del programador determinar la dimensión y
alcance de cada aplicación, pero siempre teniendo en mente
el principio de modularidad expuesto en "Filosofía".

¿Cómo crear una aplicación Django?
==================================

Una aplicación Django debe mantener la misma estructura de
directorios expuesta en el documento "Una estructura de 
directorios para aplicaciones Python", donde el código fuente
será colocado en el directorio "src".

En el caso de las pruebas, éstas deben ser un proyecto Django
sencillo que permita probar la funcionalidad de la aplicación
al estilo "prueba caja negra".


