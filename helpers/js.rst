##############
`Helper Js <https://github.com/KumbiaPHP/KumbiaPHP/blob/master/core/extensions/helpers/js.php>`_
##############

Clase que permite crear etiquetas html (links, select, entre otros) que funcionan mendiante Ajax.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo státicas, lo que nos permite usarlas directamente de la forma como se presentan a continuaci?n.

link()
====

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

linkAction()
===========

Crea un enlace en una Aplicacion actualizando la capa con ajax (solo se especifica la accion del controlador actual).

::

	$action ruta a la accion
    $text texto a mostrar
    $update capa a actualizar
    $class clases adicionales
    $attrs atributos adicionales

    Ajax::linkAction($action, $text, $update, $class = NULL, $attrs = NULL)
	
::

	/*Ejemplo*/ 
	Ajax::linkAction("listar", "Actualizar lista de usuarios", "lista-ajax")

.. php:method:: linkAction()

linkConfirm()
===========

Crea un enlace en una Aplicación actualizando la capa con ajax con mensaje de confirmación

::

	$action ruta a la accion
    $text texto a mostrar
    $update capa a actualizar
	$confirm mensaje de confirmacion
    $class clases adicionales
    $attrs atributos adicionales

    Ajax::linkConfirm($action, $text, $update, $confirm, $class = NULL, $attrs = NULL)
	
::

	/*Ejemplo*/ 
	Ajax::linkConfirm("usuarios/eliminar/$id", "Eliminar Usuario", "respuesta-ajax",'¿ Está Seguro ?')

.. php:method:: linkConfirm()

linkActionConfirm()
===========

Crea un enlace en una Aplicación actualizando la capa con ajax con mensaje de confirmación solo se especifica la accion del controlador actual).

::

	$action ruta a la accion
    $text texto a mostrar
    $update capa a actualizar
	$confirm mensaje de confirmacion
    $class clases adicionales
    $attrs atributos adicionales

    Ajax::linkActionConfirm($action, $text, $update, $confirm, $class = NULL, $attrs = NULL)
	
::

	/*Ejemplo*/ 
	Ajax::linkActionConfirm("eliminar/$id", "Eliminar Usuario", "respuesta-ajax",'¿ Está Seguro ?')

.. php:method:: linkActionConfirm()

select()
===========

Lista desplegable para actualizar usando ajax

::

	$field nombre de campo
    $data array con los pares clave|valor para las opciones del select
	$update capa que se actualizara
	$action accion que se ejecutara
	$class clases que tendra el select
	$attrs atributos adicionales

    Ajax::select($field, $data, $update, $action, $class=null, $attrs=null)
	
::

	/*Ejemplo*/ 
	$paises = array( 'Pais 1' , 'Pais 2' , ... )
	
	Ajax::select("paises", $paises, "estados-ajax" , 'controlador/obtener_estados_por_pais')

.. php:method:: select()

dbSelect()
===========

Lista desplegable para actualizar usando ajax que crea las opciones con el `Form::dbSelect() <./helpers/form.rst#dbselect>`_

::

	$field nombre de campo
    $show campo que se mostrará
	$data Array('modelo','metodo','param')
	$update capa que se actualizara
	$action accion que se ejecutara
	$class clases que tendra el select
	$attrs atributos adicionales

    Ajax::dbSelect($field, $show, $data, $update, $action, $blank=null, $class=null, $attrs=null)
	
::

	/*Ejemplo*/ 	
	Ajax::dbSelect("paises_id",'pais',NULL, 'estados-ajax' , 'controlador/obtener_estados_por_pais')

.. php:method:: dbSelect()

form()
===========

Genera un formulario Ajax

::

	$update capa que se actualizara
	$action accion a ejecutar
	$class clase de estilo
	$method metodo de envio
	$attrs atributos adicionales

    Ajax::form($update, $action = NULL, $class = NULL, $method = 'post', $attrs = NULL)
	
::

	/*Ejemplo*/ 	
	Ajax::form('respuesta-ajax')

.. php:method:: form()