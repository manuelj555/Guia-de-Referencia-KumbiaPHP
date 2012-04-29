############
Helper Tag
############

Esta clase nos va a permitir adicionar archivos JS y CSS a nuestro proyecto, bien sean archivos que se encuentren en nuestro servidor o en un servidor externo.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo státicas, lo que nos permite usarlas directamente de la forma como se presentan a continuación.

Tag::css()
===========

Incluye un archivo CSS a la lista:
::
  Tag::css('bienvenida');   //Pone en lista un CSS (app/public/css/bienvenida.css)
  echo Html::includeCss();  //Adiciona los recursos enlazados de la clase en el proyecto

.. php:method:: Tag::css()

Tag::js()
============

Incluye un archivo JavaScript a la vista, partial o template:
::
  <?php 
  echo Tag::js('jquery/jquery.kumbiaphp'); //Adiciona un archivo javascript (/app/public/javascript/jquery/jquery.kumbiaphp.js)
  ?>

.. php:method:: Tag::js()