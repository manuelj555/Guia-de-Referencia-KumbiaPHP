############
Helper Html
############

Clase con métodos estáticos con la que podemos crear etiquetas HTML optimizadas respetando las convenciones de KumbiaPHP.

.. contents:: Metodos de la clase:
  

Html::img()
===========

Permite incluir una imagen:
::
  $src ruta de la imagen
  $alt atributo alt para la imagen
  $attrs atributos adicionales
  
  img ($src, $alt=NULL, $attrs = NULL)
  
::

  /*Ejemplo*/
  echo Html::img('spin.gif','una imagen');
  //se muestra la imagen spin.gif que se encuentra dentro de "/public/img/"
  //con el artibuto alt 'una imagen'

.. php:method:: Html::img()

Html::link()
============

Permite incluir un link:
::
  $action ruta a la acción
  $text texto a mostrar
  $attrs atributos adicionales

  Html::link ($action, $text, $attrs = NULL)

::

  /*Ejemplo*/
  echo Html::link('pages/show/kumbia/status','Configuración'); 
  //se muestra un link con el texto 'Configuración'

.. php:method:: Html::link()

Html::lists()
=============

Crea una lista html a partir de un array:
::
  $array contenido de la lista
  $type por defecto ul, y si no ol
  $attrs atributos adicionales
  
  Html::lists($array, $type = 'ul', $attrs = NULL)

::

  /*Ejemplo*/
  $ar = array('Abdomen' => 'Abdomen','Brazos' => 'Brazos','Cabeza' => 'Cabeza','Cuello' => 'Cuello',
  'Genitales' => 'Genitales', 'Piernas' => 'Piernas', 'Tórax' => 'Tórax', 'Otros' => 'Otros');

  //$ar el array que contiene los items de la lista
  echo Html::lists($ar, $type = 'ol'); //Muestra una lista <ol></ol>
  
  $ar2 = array('Abdomen','Brazos','Cabeza','Cuello','Genitales','Piernas','Tórax','Otros');
  echo Html::lists($ar2, $type = 'ol'); //Muestra una lista <ol></ol>

.. php:method:: Html::lists()

Html::gravatar()
================

Incluye imágenes de gravatar.com:
::

  $email Correo para conseguir su gravatar
  $alt Texto alternativo de la imagen. Por defecto: gravatar
  $size Tamaño del gravatar. Un numero de 1 a 512. Por defecto: 40
  $default URL gravatar por defecto si no existe, o un default de gravatar. Por defecto: mm

  Html::gravatar($email, $alt='gravatar', $size=40, $default='mm')

  echo Html::gravatar( $email ); // Simple
  echo Html::link( Html::gravatar($email), $url); // Un gravatar que es un link
  echo Html::gravatar( $email, $name, 20, 'http://www.example.com/default.jpg'); //Completo

.. php:method:: Html::gravatar()

Html::includeCss()
==================

Incluye los archivos CSS que previamente fueron cargados a la lista mediante Tag::css():

::

  Tag::css('bienvenida');    //Pone en lista un CSS (app/public/css/bienvenida.css)
  echo Html::includeCss();  //Adiciona los recursos enlazados de la clase en el proyecto

.. php:method:: Html::includeCss()

Html::meta()
============

Crea un metatag y lo agrega a una lista estática que será añadida más adelante mediante Html::includeMetatags();

::

  $content contenido del metatag
  $attrs atributos adicionales del tag
  
  Html::meta($content, $attrs = NULL)
  
  Html::meta('Kumbiaphp-team',"name = 'Author'"); 
  //Agrega: <meta content="Kumbiaphp-team" name = 'Author' />
  Html::meta('text/html; charset=UTF-8',"http-equiv = 'Content-type'"); 
  //Agrega: <meta content="text/html; charset=UTF-8" http-equiv = 'Content-type' />

.. php:method:: Html::meta()

Html::includeMetatags()
=======================

Agrega los metatag que previamente se habían agregado:

::

  Html::meta('Kumbiaphp-team',"name = 'Author'");
  Html::meta('text/html; charset=UTF-8',"http-equiv = 'Content-type'");
  echo Html::includeMetatags(); //Visualiza <meta content="Kumbiaphp-team" name = 'Author'/>

.. php:method:: Html::includeMetatags()

Html::headLink()
================

Agrega un elemento de vinculo externo de tipo <link> a la cola de enlaces (para poder ser visualizado se requiere de Html::includeHeadLinks() de modo similar que Html::includeCss())

::

  $href dirección url del recurso a enlazar
  $attrs atributos adicionales
  
  Html::headLink($href, $attrs = NULL)
  
  Html::headlink('http://www.kumbiaphp.com/public/style.css',"rel='stylesheet',type='text/css' media='screen'"); 
  //Se agrega a la cola de links el enlace a un recurso externo, en este caso la hoja de estilo ubicada en "http://www.kumbiaphp.com/public/style.css"
  
  /*Agrega a la cola de links "<link rel="alternate" type="application/rss+xml" title="KumbiaPHP Framework RSS Feed" href="http://www.kumbiaphp.com/blog/feed/" />" 
    con lo cual podemos incluir un feed sin usar las convenciones de kumbiaphp */
  
  Html::headlink('http://www.kumbiaphp.com/blog/feed/',"rel='alternate' type='application/rss+xml' title='KumbiaPHP Framework RSS Feed'");
  Html::headlink('http://www.kumbiaphp.com/favicon.ico',"rel='shortcut icon',type='image/x-icon'"); 
  //Agrega la etiqueta <link> para usar un favicon externo
   
  echo Html::includeHeadLinks(); //Muestra los links que contiene la cola

.. php:method:: Html::headLink()
 
Html::headLinkAction()
======================

Agrega un elemento de vinculo interno de tipo <link> a la cola de enlaces (para poder ser visualizado se requiere de Html::includeHeadLinks() de modo similar que Html::includeCss()) respetando las convenciones de KumbiaPHP.

::

  $href dirección url del recurso a enlazar
  $attrs atributos adicionales
  
  Html::headLinkAction($action, $attrs = NULL)
  
  /*  Agrega a la cola de links 
      "<link rel="alternate" type="application/rss+xml" title="KumbiaPHP Framework RSS Feed" href="http://www.kumbiaphp.com/blog/feed/" />"
      con lo cual podemos incluir un feed usando las convenciones de KumbiaPHP.
      Siendo 'articulos/feed' el nombre de la vista con el contenido del feed */
  
  Html::headLinkAction('articulos/feed', "rel='alternate' type='application/rss+xml' title='KumbiaPHP Framework RSS Feed'");
   
  echo Html::includeHeadLinks(); //Muestra los links que contiene la cola

.. php:method:: Html::headLinkAction()

Html::headLinkResource()
=======================

Agrega un elemento de vinculo a un recurso interno con la etiqueta <link> a la cola de enlaces (para poder ser visualizado se requiere de Html::includeHeadLinks())

::

  $resource ubicación del recurso en public
  $attrs atributos adicionales
  
  Html::headLinkResource($resource, $attrs = NULL)
  
  Html::headLinkResource('favicon.ico',"rel='shortcut icon',type='image/x-icon'"); 
  //Agrega la etiqueta <link> para usar un favicon interno ubicado en el directorio '/public/'
   
  echo Html::includeHeadLinks(); //Muestra los links que contiene la cola

.. php:method:: Html::headLinkResource()

Html::includeHeadLinks()
========================

Incluye los links que previamente se pusieron en cola:

::

  Html::headlink('http://www.kumbiaphp.com/favicon.ico',"rel='shortcut icon',type='image/x-icon'"); 
  //Agrega la etiqueta <link> para usar un favicon externo
  Html::headLinkAction('articulos/feed', "rel='alternate' type='application/rss+xml' title='KumbiaPHP Framework RSS Feed'");
  echo Html::includeHeadLinks();

.. php:method:: Html::includeHeadLinks()