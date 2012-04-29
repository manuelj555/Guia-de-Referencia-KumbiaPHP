############
Helper Form
############

Clase para el manejo y la creación de formularios.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo státicas, lo que nos permite usarlas directamente de la forma como se presentan a continuación.

Form::open()
===========

Crea una etiqueta de apertura de formulario <form method="post" action="...">

::
  $action acción a  la que envía los datos, por defecto llama la misma acción de donde proviene
  $method 'POST', 'GET', 'DELETE', 'HEAD', 'PUT'. Por defecto se tiene en 'POST'
  $attrs atributos adicionales

  Form::open($action = NULL, $method = 'POST', $attrs = NULL)
::
  /*Ejemplo*/ 
  <?php echo Form::open(); ?>
  //inicia un formulario que enviara los datos a la acción que corresponde al controller actual
  
  <?php echo Form::open('usuarios/nuevo'); ?> 
  //inicia un formulario que enviara los datos al controller 'usuarios' y la acción 'nuevo'

.. php:method:: Form::open()

Form::openMultipart()
=====================

Crea una etiqueta de formulario multipart, este es ideal para formularios que contienen campos de subida de archivos:

::
	$action acción a  la que envía los datos, por defecto llama la misma acción de donde proviene
	$attrs atributos adicionales

	Form::openMultipart ($action = NULL, $attrs = NULL)
	
::
	/*Ejemplo*/
	echo Form::openMultipart();
	//inicia un formulario multipart que enviara los datos a la acción que corresponde a la vista actual
	echo Form::openMultipart('usuarios/nuevo');
	//inicia un formulario multipart que enviara los datos al controller 'usuario' y la acción 'nuevo'

.. php:method:: Form::openMultipart()