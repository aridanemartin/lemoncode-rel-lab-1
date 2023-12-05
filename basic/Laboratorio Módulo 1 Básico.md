# Enunciado del ejercicio

Una startup tecnológica va a desarrollar un portal de ELearning y nos ha pedido que realizamos el modelo de datos de dicho sistema.

A tener en cuenta:

Va a ser un portal orientado al mundo de la programación.
El portal va a estar compuesto por cursos, cada curso está compuesto a su vez por un número de videos y artículos que lo acompañen.
La página de cursos debe mostrar la lista de autores que lo hicieron.
La página de un video debe mostrar el autor que lo realizó.
Los videos y el contenido de cada artículo se almacenan en un storage S3 y en un headless CMS, en la base de datos sólo almacenaremos los Id's a esos recursos.
Los videos se pueden clasificar por temáticas (Devops / Front End / Back End / ...)
Los videos tienen autores (ponemos la restricción, un video tiene un autor), un curso puede tener varios autores.
En principio los vídeos no se van a compartir entre diferentes cursos (aunque sería una amplicacíon interesante del ejercicio.
Hay una opción para ver la página con la biografía del autor.

# Tablas

_Course_ => Es la tabla principal y tiene una relación de muchos a muchos con Lesson ya que un curso puede tener muchas lecciones pero una lección también debe poder aparecer en más de un curso. Ej. La lección de figma puede pertenecer a los cursos de UX y FE indistintamente.

_Lesson_ => Las lecciones tienen una relación de 1 a 1 con los vídeos ya que cada lección tiene un solo vídeo explicativo.

_Video_ => Pertenece a una sola lección y está relacionado con uno o varios temas por eso la relación de muchos a muchos. Sólo pueden tener un autor.

_Autors_ => Un curso puede tener varios de ellos y un autor puede ser ponente de varios cursos. En cuanto a su relación con los vídeos es diferente porque un vídeo solo puede tener un autor.
