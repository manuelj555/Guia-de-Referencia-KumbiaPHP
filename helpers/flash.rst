##############
`Helper Flash <https://github.com/KumbiaPHP/KumbiaPHP/blob/master/core/extensions/helpers/flash.php>`_
##############

Clase que permite hacer la salida de mensajes de error, advertencia, informativos y éxito de forma estándar.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo státicas, lo que nos permite usarlas directamente de la forma como se presentan a continuaci�n.

valid()
===========

Muestra un mensaje de exito en la pantalla.

::

	$text texto que se mostrará en pantalla
	
	Flash::valid($text)
::

	/*Ejemplo*/ 
	Flash::valid("Se creó el registro exitosamente...!!!")

.. php:method:: valid()

info()
===========

Muestra un mensaje de información en la pantalla.

::

	$text texto que se mostrará en pantalla
	
	Flash::info($text)
::

	/*Ejemplo*/ 
	Flash::info("Bienvenido al Sistema")

.. php:method:: info()

warning()
================

Muestra un mensaje de advertencia en la pantalla.

::

	$text texto que se mostrará en pantalla
	
	Flash::warning($text)
::

	/*Ejemplo*/ 
	Flash::warning("La contraseña es muy corta...!!!")

.. php:method:: warning()

error()
================

Muestra un mensaje de error en la pantalla.

::

	$text texto que se mostrará en pantalla
	
	Flash::error($text)
::

	/*Ejemplo*/ 
	Flash::error("Error: el campo usuario no puede ser Nulo...!!!")

.. php:method:: error()

show()
================

Muestra un mensaje Flash en la pantalla.

::

	$name	Tipo de mensaje y clase tendra para el CSS class='$name'.
	$text 	Mensaje a mostrar
	
	Flash::show($name, $text)
::

	/*Ejemplo*/ 
	Flash::show("error", "Error: el campo usuario no puede ser Nulo...!!!")

.. php:method:: show()