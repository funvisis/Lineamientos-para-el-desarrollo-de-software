======================================================
Una estructura de directorios para aplicaciones Python
======================================================

:Autor:
	"Daniel Ampuero" <danielmaxx@gmail.com>

:Versión: 1.0 24/04/2012

El fundamento de este documento puede ser encontrado en el documento
*¿Cómo desarrollar proyectos de software?*. En este documento, me
reduciré a explicar la estructura de directirios para proyectos
Python y el porqué de las mismas.

¿Qué es un proyecto Python?
===========================

Aún cuando la palabra "proyecto" suene a algo grande, es decir, muchas
piezas de software integradas, en el ámbito de este documento y para
los fines del desarrollo mismo de software se definirá como "Proyecto
Python" a un conjunto de módulos Python que resuelvan un problema
particular. Estos módulos deben ser capaces de ser independientes y
acoplables a cualquier otro proyecto Python. Coloquialmente: un poco
siguiendo la onda Unix de "Escribe programas que hagan una cosa, y 
que la hagan bien".

¿Qué debe incluir un proyecto Python?
=====================================

Un Proyecto Python debe incluir tres cosas fundamentales:

- Código fuente: este debe ser colocado en un directorio llamado "src". Aún
cuando algunos no recomiendan el uso de "src" como nombre de directorio para
contener los fuentes, éste sigue siendo un nombre muy obvio para contener
archivos fuentes y facilita el proceso de instalación. Para evitar problemas
con el nombre de los paquetes, es necesario escribir el archivo *setup.py* el
nombre que se desea dar a los paquetes, y de esta forma no tener paquetes 
llamados "src.funvisis.blah.bloh...".

- Pruebas: deben ir en un directorio separado de los fuentes llamado "test".
Dentro del mismo, se debe hacer una distinción (a través de directorios) de
las pruebas unitarias y de las pruebas de caja negra.

- Documentación: deben ir en un directorio llamado doc.

Aparte de eso, todo proyecto Python debe ser instalable. Por tal motivo,
es importante hacer un *setup.py* por cada proyecto e incluir los respectivos
*__init.py__* por cada paquete que se desea distribuir de ese proyecto.

Adicionalmente, todo proyecto Python debe incluir los siguiente en su
directorio raíz:

- LICENCE.txt: contiene la licencia de distribución del proyecto. Usa alguna que
sea conocida, como GPL, BSD o MIT.
- MANIFEST.in: este archivo debe contener esto:

    include *.txt
    recursive-include docs *.txt

- README.txt: deben ser escritos en reST para que PyPI pueda procesarlo automáticamente
y generar una página de proyecto PyPI. Éstos deben proveer el vistazo inicial al
proyecto, i.e., qué hace, cómo se instala, qué necesita y cualquier otra cosa
que se considere necesario.

Un asunto delicado: escribir *setup.py*
=======================================

Aunque *setup.py* pueda parecer sencillo, éste encierra algunos trucos y puntos
importantes a tratar.

La estructura propuesta para *setup.py* es la siguiente:

    # -*- coding: utf-8 -*-

    from distutils.core import setup

    setup(name='',
          version='',
          author='',
          author_email='',
          url='',
          download_url='',
          description='',
          long_description='',
          packages=[''],
          package_dir={'':'src'},
          py_modules=[''],
          provides=[''],
          keywords='',
          license='',
          classifiers=['Development Status :: Alpha',
                       'Intended Audience :: Developers',
                       'Natural Language :: English',
                       'Operating System :: OS Independent',
                       'Programming Language :: Python :: 2.6+',
                       'License :: OSI Approved :: GNU Library or Lesser General Public License (LGPL)',
                       'License :: OSI Approved :: GNU Affero General Public License v3',
                       'Topic :: Internet',
                       'Topic :: Scientific/Engineering :: GIS',
                      ],
           requires=[''],
         )

IMPORTANTE: los campos que se describen a continuación deben ser rellenados en su totalidad.
Aquellos campos que NO SE VAYAN A UTILIZAR, se deben BORRAR.

De todos los campos que se especifican arriba, tomaremos atención de los
siguientes:

- packages: debe contener la lista de paquetes que queremos instalar y el
nombre que les queremos dar. Por ejemplo, si queremos instalar el paquete
"funvisis.geo.buildings", entonces "packages" debe tener la siguiente estructura:

    packages = ['funvisis', 'funvisis.geo', 'funvisis.geo.buildings']

Es importante saber que los paquetes declarados deben ser consistentes con
una estructura de directorios. En este ejemplo, la estructura de directorios
sería la siguiente:

- funvisis
   | __init.py__
   | geo
      | __init.py__
      | buildings
         | __init.py__

- package_dir: este diccionario indica dónde empezar a buscar los paquetes y su
relación con el espacio de nombres. Usualmente se usará el que se muestra en
el ejemplo, pues queremos que la raíz de los paquetes empiece en "src" y no
lo incluya como paquete.

- requires: debe indicar los paquetes Python requeridos por este proyecto
para poder funcionar.










