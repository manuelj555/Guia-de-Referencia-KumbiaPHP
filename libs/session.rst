####
`Session <https://github.com/KumbiaPHP/KumbiaPHP/blob/master/core/libs/session/session.php>`_
####

Modelo orientado a objetos para el acceso a datos en Sesiones.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo estáticas, lo que nos permite usarlas directamente de la forma como se presentan a continuación.

set()
====

Crear o especificar el valor para un indice de la sesión actual.

::

    Session::set($index, $value, $namespace='default)
	
.. php:method:: set()

get()
====

Obtener el valor para un indice de la sesión.

::

    Session::get($index, $namespace='default')
	
.. php:method:: get()

delete()
====

Elimina un indice de la sesión.

::

    Session::delete($index, $namespace='default')
	
.. php:method:: delete()

has()
====

Verifica si el indice esta cargado en sesión.

::

    Session::has($index, $namespace='default')
	
.. php:method:: has()
