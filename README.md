Objetivo Crear una aplicación web visual e interactiva que permita explorar libros, descubrir autores y ver detalles de obras usando la API pública de Open Library.

Este proyecto tiene como finalidad practicar:

Uso de rutas dinámicas con Fresh Consumo de APIs públicas desde el servidor Estilizado con CSS moderno (grid, efectos hover) Separación de lógica y componentes Requisitos funcionales Página principal / Mostrar un grid de 3 columnas con libros predefinidos, a partir de un array de títulos (ver más abajo). Para cada título, deberás consultar la API: https://openlibrary.org/search.json?q={titulo} Usar el campo "key": "/works/OL3140822W" para obtener el ID del libro, eliminando /works/ y dejando solo OL3140822W. Cada tarjeta del grid debe incluir: Imagen de portada (si está disponible): https://covers.openlibrary.org/b/id/{cover_i}-L.jpg Título del libro Autor Enlace a /book/[id] Las tarjetas deben tener estilo visual, con efecto hover que destaque la tarjeta al pasar el ratón.

Ruta /search Página con una barra de búsqueda para buscar libros por título. Consulta la API: https://openlibrary.org/search.json?q={titulo} Muestra los resultados en el mismo grid de 3 columnas. Si no hay resultados, mostrar mensaje: “No se encontraron libros con ese título.”

Ruta /book/[id] Página de detalles de un libro. Consulta: https://openlibrary.org/works/{id}.json Mostrar: Título Descripción (si está disponible) Año de publicación (created.date o first_publish_date) Número de páginas (si se encuentra) Imagen de portada Autor, con enlace a /author/[id] El ID del autor se obtiene de authors[0].author.key, quitando /authors/

Ruta /author/[id] Página con información sobre el autor: https://openlibrary.org/authors/{id}.json https://openlibrary.org/authors/{id}/works.json Mostrar: Nombre Biografía (si está disponible) Grid de 3 columnas con 5-6 libros del autor, cada uno enlazado a /book/[id]

Diseño y UX El grid debe ser de 3 columnas fijas Estilo limpio, visual y con CSS Efectos hover para resaltar tarjetas Cabecera fija con: Nombre del sitio

Array base de libros const featuredBooks = [ "To Kill a Mockingbird", "1984", "The Great Gatsby", "Pride and Prejudice", "The Hobbit", "Moby-Dick", "Jane Eyre", "War and Peace", "The Catcher in the Rye", "Brave New World", "The Lord of the Rings", "Crime and Punishment", "The Alchemist", "The Picture of Dorian Gray", "Harry Potter and the Sorcerer's Stone" ];
