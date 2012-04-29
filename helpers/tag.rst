############
`Helper Tag <https://github.com/KumbiaPHP/KumbiaPHP/blob/master/core/extensions/helpers/tag.php>`_
############

Esta clase nos va a permitir adicionar archivos JS y CSS a nuestro proyecto, bien sean archivos que se encuentren en nuestro servidor o en un servidor externo.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo státicas, lo que nos permite usarlas directamente de la forma como se presentan a continuación.

css()
===========

Incluye un archivo CSS a la lista:

::

  Tag::css('bienvenida');   //Pone en lista un CSS (public/css/bienvenida.css)
  echo Html::includeCss();  //Adiciona los recursos enlazados de la clase en el proyecto

.. php:method:: css()

js()
============

Incluye un archivo JavaScript a la vista, partial o template:
::

  echo Tag::js('jquery/jquery.kumbiaphp'); 
  //Adiciona un archivo javascript (/public/javascript/jquery/jquery.kumbiaphp.js)

.. php:method:: `Tag::js() js()