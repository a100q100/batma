==================
Instalando o Batma
==================

.. contents:: Índice

------------
Dependências
------------

- Python 2.7 *~duh~* (não foi testado no 2.6 ou menores)
  (http://www.python.org)

- PyGame 1.9.1
  (http://pyglet.org/)


----------
Instalação
----------

Instalar usando o easy_install
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Via **easy_install** é o jeito mais fácil de instalar o Batma, ele também vai 
instalar a PyGame se não encontrá-lo no sistema::

    easy_install batma


Instalar usando o setup.py
~~~~~~~~~~~~~~~~~~~~~~~~~~

Faça o download do `último release do Batma <http://renatopp.github.com/batma/>`_, 
descompacte em algum diretório e execute::

    python setup.py install


Instalar pelo jeito difícil
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Faça o download do `último release do Batma <http://renatopp.github.com/batma/>`_, 
descompacte em algum diretório e execute:

**No Windows**::

    set PYTHONPATH c:\caminho\para\o\batma\;%PYTHONPATH%

**Linux, Mac OS X ou Windows usando cygwin**::
    
    set PYTHONPATH /camingo/para/o/batma/:$PYTHONPATH
    export PYTHONPATH


-----------------------
Testando sua instalação
-----------------------

Se tudo correu bem, abra o terminal (no windows o cmd) e digite::

    $ python -c "import batma"

Se nada acontecer é porque está tudo funcionando.


