# Laboratorio Modulo 1

En este markdown explicaré el por qué del diseño de las diferentes colecciones y documentos.

### social_link

Este documento lo he creado para guardar las diferentes plataformas de un autor a modo de key/value con el patron atributo, ya que los autores pueden tener redes sociales pero no todos tienen, ni tienen las mismas.

### authors
En la coleccion de autores simplemente he querido aplicar el patron de atributo, ya que en ninguna parte es necesaria enseñar mas informacion de un autor que en el perfil del mismo, que al fin y al cabo es solo enseñar la biografia y sus redes sociales. Cualquier otra cosa que pongamos solo haria de agrandar el working set.

### courses
En la coleccion de cursos y lecciones, he decidido utilizar el subset pattern, ya que en la pagina de cursos se muestran solo los principales detalles de los cursos, la idea es no cargar mucho cada curso, y obtener las lecciones ya dentro de la vista del curso con toda su informacion. Tambien aqui guardamos si el curso es publico y la categoria.

### lessons
Las lecciones contienen la referencia al curso al que pertenece(extended ref pattern), la descripcion de la leccion y los videos que la componen, tambien contiene un boolean para saber si es publico o no, no todas las lecciones de un curso tienen por que ser publicos.

### videos
Los videos ya estan incluidos como array en cada leccion y he decidido tambien utilizar el subset pattern para tener en cada video quien fue el autor y no tenerlos cargados en cada elemento de autor. Tambien he añadido el campo topic que es un array para filtrar por tematica de video. El campo views es un campo de v alor aproximado, utilizando el patron de aproximacion, de esta manera no enviamos tantas peticiones por cada view del video.

### categories
Las categorias se guardaran basandose en el patron de Tree Pattern - Materialized paths, de esta forma podremos saber las categorias padre.

### users
En el caso de los usuarios, cada usuario contiene los cursos pagados, en este caso se pueden precalcular los 5 ultimos cursos pagados y añadir una tabla para los cursos de mas. Las suscripciones se almacenaran en el usuario tambien, siempre teniendo la suscripcion activa y en caso de no estar activa, la mas reciente, ene ste caso podriamos usar el patron extended ref.




