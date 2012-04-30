##############
`Helper Ajax <https://github.com/KumbiaPHP/KumbiaPHP/blob/master/core/extensions/helpers/ajax.php>`_
##############

Clase que permite crear etiquetas html (links, select, entre otros) que funcionan mendiante Ajax.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo státicas, lo que nos permite usarlas directamente de la forma como se presentan a continuaci?n.

link ()
===========

Crea un enlace en una Aplicacion actualizando la capa con ajax.

::

	$action ruta a la accion
    $text texto a mostrar
    $update capa a actualizar
    $class clases adicionales
    $attrs atributos adicionales

    Ajax::link($action, $text, $update, $class = NULL, $attrs = NULL)
	
::

	/*Ejemplo*/ 
	Ajax::link("usuarios/listar", "Actualizar lista de usuarios", "lista-ajax")

.. php:method:: link()