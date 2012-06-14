===================================================
Una estructura de directorios para proyectos Django
===================================================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>

:Versión: 1.0 21/05/2012


La motivación del presente documento es presentar un Layout para
proyectos Django que siga y promueva los principios expuestos en
"Filosofía".


¿Qué es un proyecto Django?
===========================

Básicamente un proyecto Django es una colección de aplicaciones
Django. Si bien una aplicación puede existir por sí misma, un
proyecto necesita la integración de al menos una aplicación para
existir. Por tal motivo, es importante separar y distinguir 
apropiadamente las partes de un proyecto de las partes de una 
aplicación.

Antes de empezar, debemos recordar que siempre debemos trabajar
en ambientes virtuales, bien sea por virtualenv o con debootstrap.

Layout base
===========

La última versión de Django (1.4 a la fecha), introdujo algunos
cambios con respecto a las versiones anteriores en el tema de
la disposición de los archivos. Lo que más llama la atención es
la separación del archivo manage.py de los archivos del proyecto,
lo cual tiene todo el sentido del mundo pues manage.py NO FORMA
PARTE DEL PROYECTO, sino que es un script con múltiples herramientas.

De esta forma, el layout base de un proyecto Django (el cual llamaremos
de forma muy original bar) es el siguiente:

- bar
   | manage.py
   | bar
      | settings.py
      | urls.py
      | __init__.py

Con este sencillo layout, ya es posible hacer un proyecto Django
funcional.

Archivo de configuración
========================

En el mundo Django, es muy común tener dos configuraciones: una
para desarrollo y otra para producción. En tal sentido, una forma
inteligente de resolver tal diatriba es poseer tres archivos de
configuración: 

- settings_base: la configuración básica y común a las fases de
desarrollo y producción. 
- settings_dev: configuración para entorno de desarrollo.
- settings_prod: configuración para el entorno de producción.

Puesto que Django supone la existencia de settings.py en el proyecto,
existen dos soluciones posibles:

- Hacer un enlace simbólico
- Crear un archivo settings.py e importar el módulo apropiado.

Cualquiera de las dos soluciones son válidas y depende del gusto y
estilo del programador.

Layout extendido
================

El layout base presentado anteriormente es adecuado para proyectos
de prueba. En cambio, a la hora de hacer un proyecto más grande y
ambicioso, es preciso contemplar otras cosas.

El siguiente es la estructura de directorios para un proyecto Django
(el cual, evidentemente, sigue llamándose "bar"):

- bar
   | manage.py
   | doc            # Documentación del proyecto
   | README         # Se explican los requisitos del proyecto
   | static         # {.html, .js, .css, .jpg, .png, etc}
   | templates      # Templates de Django
   | requirements.pip # Requisitos para virtualenv
   | non_python_req # Un archivo de texto plano
   | deployment     # Un directorio dedicado a la puesta en producción
   | fixtures       # Datos iniciales. En caso de no existir, dejar vacío
   | bar
      | settings.py
      | urls.py
      | __init__.py      



