##############
`Helper Js <https://github.com/KumbiaPHP/KumbiaPHP/blob/master/core/extensions/helpers/js.php>`_
##############

Clase que permite crear etiquetas html (links, select, entre otros) que funcionan mendiante Ajax.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo státicas, lo que nos permite usarlas directamente de la forma como se presentan a continuaci?n.

link()
====

Crea un enlace en una Aplicacion con mensaje de confirmacion respetando las convenciones de Kumbia.

::

	$action ruta a la accion
    $text texto a mostrar
    $confirm mensaje de confirmacion
    $class clases adicionales
    $attrs atributos adicionales

    Js::link($action, $text, $confirm = '¿Está Seguro?', $class = NULL, $attrs = NULL)
	
::

	/*Ejemplo*/ 
	Js::link("admin/usuarios/eliminar/$id", 'Eliminar User')

.. php:method:: link()

linkAction()
====

Crea un enlace en una Aplicacion con mensaje de confirmacion respetando las convenciones de Kumbia (solo se especifica la accion del controlador actual).

::

	$action ruta a la accion
    $text texto a mostrar
    $confirm mensaje de confirmacion
    $class clases adicionales
    $attrs atributos adicionales

    Js::linkAction($action, $text, $confirm = '¿Está Seguro?', $class = NULL, $attrs = NULL)
	
::

	/*Ejemplo*/ 
	Js::linkAction("eliminar/$id", 'Eliminar User')

.. php:method:: linkAction()

submit()
====

Crea un boton submit con mensaje de confirmacion respetando las convenciones de Kumbia.

::

    $text texto a mostrar
    $confirm mensaje de confirmacion
    $class clases adicionales
    $attrs atributos adicionales

    Js::submit($text, $confirm = '¿Está Seguro?', $class = NULL, $attrs = NULL)
	
::

	/*Ejemplo*/ 
	Js::submit("eliminar/$id", 'Eliminar User')

.. php:method:: submit()

submitImage()
====

Crea un boton de tipo imagen con mensaje de confirmacion respetando las convenciones de Kumbia.

::

    $img imagen a mostrar en el submit
    $confirm mensaje de confirmacion
    $class clases adicionales
    $attrs atributos adicionales

    Js::submitImage($img, $confirm = '¿Está Seguro?', $class = NULL, $attrs = NULL)
	
::

	/*Ejemplo*/ 
	Js::submitImage("mi_imagen.jpg", '¿ Estas seguro de eliminar el Registro ?')

.. php:method:: submitImage()
