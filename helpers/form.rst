############
`Helper Form <https://github.com/KumbiaPHP/KumbiaPHP/blob/master/core/extensions/helpers/form.php>`_
############

Clase para el manejo y la creación de formularios.

.. contents:: Metodos de la clase:
  
Las funciones de esta clase son de tipo státicas, lo que nos permite usarlas directamente de la forma como se presentan a continuación.

open()
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

.. php:method:: open()

openMultipart()
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

.. php:method:: openMultipart()

close()
=============

Crea una etiqueta de cierre de formulario:

::

	/*Ejemplo*/
	echo Form::close();
	//crea una etiqueta de cierre de formulario </form>

.. php:method:: close()

input()
=============

Crea un campo de tipo input:

::

	$attrs atributos para el tag
	$content contenido interno

	Form::input($attrs = NULL, $content = NULL)

::
	
	/*Ejemplo*/
	echo Form::input('nombre');

.. php:method:: input()

text()
============

Crea un campo de tipo input:

Siempre que se le da el parámetro name de la forma model.campo, es decir un nombre que contenga un punto dentro del string, se crea el campo de texto con el name= "model[campo]" y el id="model_campo".

::

	$field Nombre de campo
	$attrs atributos de campo
	$value valor inicial para el input

	Form::text($field, $attrs = NULL, $value = NULL)

::

	/*Ejemplo*/
	echo Form::text('nombre'); 
	//crea un campo de tipo texto con el parámetro name= "nombre", id = "nombre"
	
	echo Form::text('usuario.nombre'); 
	//crea un campo de tipo texto con el parámetro name= "usuario[nombre]", id = "usuario_nombre"
	
	echo Form::text('nombre',"class= 'caja'",'55'); 
	//crea un campo de tipo texto con el parámetro name= "nombre", id = "nombre", class= "caja", value = "55"

.. php:method:: text()

pass()
===========

Crea un campo de tipo Password:

::

	$field nombre de campo
	$attrs atributos de campo
	$value valor inicial para el campo

	Form::pass($field, $attrs = NULL, $value = NULL)

::

	/*Ejemplo*/
	echo Form::pass('password'); //crea un campo de tipo password con el parámetro name= "password"

.. php:method:: pass()

textarea()
================

Crea un textarea:

::

	$field nombre de campo
	$attrs atributos de campo
	$value valor inicial para el textarea

	Form::textarea($field, $attrs = NULL, $value = NULL)

	echo Form::textarea('detalles'); //Crea un textarea

.. php:method:: textarea()

label()
=============

Crea un label y lo asocia a un campo:

::

	$text texto a mostrar
	$field campo al que hace referencia
	$attrs array de atributos opcionales

	Form::label($text, $field, $attrs = NULL)

	echo Form::label('nombre de usuario:','nombre'); 
	//Crea un label para el campo nombre con el texto 'nombre de usuario:'
	
	echo Form::text('nombre');

.. php:method:: label()

hidden()
==============

Crea un campo hidden (campo oculto):

::

	$field nombre de campo
	$attrs atributos adicionales de campo
	$value valor inicial para el campo oculto

	Form::hidden($field, $attrs = NULL, $value = NULL)

	echo Form::hidden( 'id', NULL, 12); //Crea un campo oculto con el name="id" y el value="12"

.. php:method:: hidden()

dbSelect()
================

Crea campo Select que toma los valores de objetos de ActiveRecord, para esta versión del framework el uso de este helper ha sido simplificado. Ya no es necesario instanciar el modelo.

::

	$field nombre del modelo y campo pk (bajo la convención modelo.campo_id)
	$show campo que se mostrara
	$data array de valores, array('modelo','metodo','param')
	$blank campo en blanco
	$attrs atributos de campo
	$value valor inicial para el campo

	Form::dbSelect($field, $show = NULL, $data = NULL, $blank = NULL, $attrs = NULL, $value = NULL)

	//En la Vista
	echo Form::dbSelect('usuarios.campo_id'); //la forma más fácil, carga el modelo(campo) y muestra el primer campo después del pk(id)
	echo Form::dbSelect('usuarios.campo_id', 'campo'); //muestra el campo y lo ordena ascendentemente 

.. php:method:: dbSelect()

select()
==============

Crea un campo Select (un combobox):

::

	$field nombre de campo
	$data array de valores para la lista desplegable
	$attrs atributos de campo
	$value valor inicial para el campo

	Form::select($field, $data, $attrs = NULL, $value = NULL)

	$ar2 = array('Abdomen','Brazos','Cabeza','Cuello','Genitales','Piernas','Tórax','Otros');
	echo Form::select('region', $ar2, NULL, 'Cuello'); 
	//Crea un campo Select (un combobox) con el nombre 'region' y teniendo preseleccionado 'Cuello'

	//Resultado:
	<select id="region" name="region">
		<option value="0">Abdomen</option>
		<option value="1">Brazos</option>
		[...]
	</select>


	//Otra Posibilidad:
	$ar2 = array('Abdomen'=>'Abdomen','Brazos'=>'Brazos','Cabeza'=>'Cabeza','Cuello'=>'Cuello',
	'Genitales'=>'Genitales','Piernas'=>'Piernas','Tórax'=>'Tórax','Otros'=>'Otros');
	
	echo Form::select('region', $ar2, NULL, 'Cuello');

	//Resultado:
	<select id="region" name="region">
		<option value="Abdomen">Abdomen</option>
		<option value="Brazos">Brazos</option>
		[...]
	</select>

.. php:method:: select()

file()
============

Crea campo File para subir archivos, el formulario se debe abrir con Form::openMultipart():

::

	$field nombre de campo
	$attrs atributos de campo

	Form::file($field, $attrs = NULL)

	echo Form::openMultipart(); //Abre el formulario multipart
	echo Form::file('subir'); crear el campo para subir archivos
	echo Form::close(); //Cierra el formulario

.. php:method:: file()
	
button()
=============

Crea una etiqueta button:

::

	$text texto del botón
	$attrs atributos del botón

	Form::button($text, $attrs = NULL)

	echo Form::button('calcular'); //Crea un botón con el texto 'calcular'

.. php:method:: button()

submitImage()
==================

Crea un botón de tipo imagen siguiendo las convenciones de KumbiaPHP, la imagen deberá estar dentro del directorio '/public/img/':

::

	$img ruta de la imagen que usa el botón
	$attrs atributos del botón

	Form::submitImage($img, $attrs = NULL)

	echo Form::submitImage('botones/edit.gif'); 
	//Crea un botón con la imagen 'botones/edit.gif'

.. php:method:: submitImage()

submit()
==============

Crea un botón de submit para el formulario actual:

::

	$text texto del botón
	$attrs atributos del botón

	Form::submit($text, $attrs = NULL)

	echo Form::submit('enviar'); //Crea un botón con el texto 'enviar'

.. php:method:: submit()
	
reset()
=============

Crea un botón reset para el formulario actual:

::

	$text texto del botón
	$attrs atributos del botón

	Form::reset($text, $attrs = NULL)

	echo Form::reset('reiniciar'); //Crea un botón con el texto 'reiniciar'

.. php:method:: reset()
	
check()
=============

Crea un checkbox:

::

	$field nombre de campo
	$value valor en el checkbox
	$attrs atributos de campo
	$checked indica si se marca el campo

	Form::check($field, $value, $attrs = NULL, $checked = NULL)

	echo Form::check('recuerdame','1','',true); 
	// Crea un check seleccionado con id="recuerdame" , name="recuerdame" y value="1"
	
	echo Form::check('recuerdame','1','',false); 
	// Crea un check NO seleccionado con id="recuerdame" , name="recuerdame" y value="1"

.. php:method:: check()

radio()
=============

Crea un radio button:

::

	$field nombre de campo
	$value valor en el radio
	$attrs atributos de campo
	$checked indica si se marca el campo

	Form::radio($field, $value, $attrs = NULL, $checked = NULL)

	$on = 'masculino';
	echo Form::radio("rdo", 'masculino', NULL, TRUE);  
	//<input id="rdo1" name="rdo" type="radio" value="masculino" checked="checked">
	
	echo Form::radio("rdo", 'femenino'); 
	//<input id="rdo2" name="rdo" type="radio" value="femenino">
	
.. php:method:: radio()