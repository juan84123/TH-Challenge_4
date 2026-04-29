1️⃣ Escenario y Desafío ❄️

Después de escapar del laberinto, refactorizar tu alma en clases y salvar al mundo con sockets, creíste que habías alcanzado la paz… Pero no.

Sos ahora el detective de datos peor pagado del hemisferio sur. Tu escritorio: un Jupyter Notebook. Tu arma: SELECT. Tu jefe: un pingüino que solo dijo:

    “Hacelo por el bien de la literatura… y por los memes.”

Tu nueva misión:
Infiltrarte en el criminalmente desactualizado sitio Books To Scrape y exponer verdades oscuras como:

    ¿Qué autor sigue publicando catástrofes de 1 estrella?
    ¿Quién es el capo de la literatura barata pero bien rankeada?
    ¿Y por qué hay tantos libros amarillos?

Pero ahora hay una condición adicional: Los autores NO pueden cargarse manualmente. Deben ser enriquecidos utilizando una API externa. Sin API, el challenge está incompleto.

Tenés 1 semana. Sin comodines. Sin frameworks mágicos. Solo Google, BeautifulSoup, requests y tu resiliencia emocional.
2️⃣ Habilidades que vas a tener que invocar

    🕷️ Web scraping legal con BeautifulSoup o requests.
    🌐 Consumo de API REST externa.
    🧱 Modelado de bases de datos relacionales.
    📊 Diagramas UML.
    📖 Consultas básicas: SELECT, JOIN, WHERE, GROUP BY.
    🧙 Consultas complejas: subconsultas, funciones de ventana.
    ⚡ Indexación y análisis de performance.
    🛑 Manejo de errores y normalización de datos.

3️⃣ Integración Obligatoria con API

Además del scraping completo del sitio, deberás:

    Extraer el nombre del autor desde la página del libro.
    Consultar una API pública para enriquecer la información del autor.
    Persistir los datos enriquecidos en la base de datos.

APIs permitidas:

    Open Library
    Google Books
    Wikipedia

Datos mínimos obligatorios a obtener:

    Año de nacimiento (si existe).
    País o nacionalidad.
    ID externo del autor.
    Cantidad aproximada de obras (si la API lo permite).
    Fuente de la API utilizada.

Manejo obligatorio:

    Control de errores (404, rate limit, timeouts).
    Si el autor no existe en la API → guardar NULL y registrar el caso.
    No duplicar llamadas innecesarias (cache recomendado).

4️⃣ Base de Datos Bien Estructurada

Modelo obligatorio: Relación muchos a muchos: Libros ↔ Autores.

Tablas mínimas esperadas:

    books: id, title, price, rating, category_id.
    authors: id, name, birth_year, country, external_api_id, total_known_works, api_source, created_at.
    book_author: book_id, author_id.
    categories: id, name.

Requisitos técnicos:

    DDL completo (CREATE TABLE) y DML (INSERT INTO).
    Claves primarias y foráneas.
    Índices correctamente definidos.
    Diagrama UML obligatorio.

5️⃣ Scraping Completo

Debés scrapear:

    Todas las categorías.
    Todos los libros.
    Sin excepciones. Si te salteás un género, el pingüino lo sabe.

6️⃣ Consultas con Emoción

Mínimo 5 consultas útiles comentadas. Ejemplo:

    Libros con más de 3 estrellas por menos de £10.
    Autor con peor promedio de rating (mínimo 5 libros).
    Categoría con mayor precio promedio.
    Top 5 autores con más libros.
    Consulta por país (Obligatoria): ¿Qué país produce más libros con rating mayor a 3 estrellas?
        Requiere: JOIN books → JOIN book_author → JOIN authors → GROUP BY country.
        Sin la API, esta consulta no existe.

7️⃣ Indexación y Performance

Debés:

    Crear una consulta deliberadamente lenta.
    Medir su tiempo de ejecución.
    Agregar índice.
    Medir nuevamente y explicar la diferencia.

8️⃣ Entregables Obligatorios

Jupyter Notebook incluyendo:

    Código de scraping y consumo de API funcional.
    Manejo de errores y base de datos creada desde cero.
    Diagrama UML.
    5 consultas comentadas (incluyendo la obligatoria por país).
    Evidencia de indexación "antes y después".
    Prueba de que los datos provienen de la API.

Nada de .sql sueltos. Nada de “confíen en mí”.
🎁 Bonus XP

    📊 Convertir una consulta en gráfico.
    📡 Implementar sistema de cache para la API.
    📈 Reportar porcentaje de autores no encontrados.
    🐍 Automatizar parte del pipeline con SQLAlchemy o Pandas.

    Nota final: Este challenge simula un mini pipeline de datos real: Scraping → Enriquecimiento → Persistencia → Modelado → Performance. Ya no es solo “hacer SELECT”.
