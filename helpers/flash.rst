##############
`Helper Flash <https://github.com/KumbiaPHP/KumbiaPHP/blob/master/core/extensions/helpers/flash.php>`_
##############

Clase que permite hacer la salida de mensajes de error, advertencia, informativos y �xito de forma est�ndar.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo st�ticas, lo que nos permite usarlas directamente de la forma como se presentan a continuaci�n.

Flash::valid()
===========

Muestra un mensaje de exito en la pantalla.

::

	$text texto que se mostrar� en pantalla
	
	Flash::valid($text)
::

	/*Ejemplo*/ 
	Flash::valid("Se cre� el registro exitosamente...!!!")

.. php:method:: Flash::valid()

Flash::info()
===========

Muestra un mensaje de informaci�n en la pantalla.

::

	$text texto que se mostrar� en pantalla
	
	Flash::info($text)
::

	/*Ejemplo*/ 
	Flash::info("Bienvenido al Sistema")

.. php:method:: Flash::info()

Flash::warning()
================

Muestra un mensaje de advertencia en la pantalla.

::

	$text texto que se mostrar� en pantalla
	
	Flash::warning($text)
::

	/*Ejemplo*/ 
	Flash::warning("La contrase�a es muy corta...!!!")

.. php:method:: Flash::warning()

Flash::error()
================

Muestra un mensaje de error en la pantalla.

::

	$text texto que se mostrar� en pantalla
	
	Flash::error($text)
::

	/*Ejemplo*/ 
	Flash::error("Error: el campo usuario no puede ser Nulo...!!!")

.. php:method:: Flash::error()

Flash::show()
================

Muestra un mensaje Flash en la pantalla.

::

	$name	Tipo de mensaje y clase tendra para el CSS class='$name'.
	$text 	Mensaje a mostrar
	
	Flash::show($name, $text)
::

	/*Ejemplo*/ 
	Flash::show("error", "Error: el campo usuario no puede ser Nulo...!!!")

.. php:method:: Flash::show()