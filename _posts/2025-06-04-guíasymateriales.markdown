---
layout: post
title:  Guías: Omeka, para repositorios; Dublin Core, para metodología metadatos; MapHub, mapas y cartografía digital
date:   2025-06-17
categories: [resources, HD]
---

<style>
  table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 1em;
  }
  th, td {
    padding: 0.5em;
    border: 1px solid #ccc;
    text-align: left;
  }
  @media screen and (max-width: 768px) {
    table, thead, tbody, th, td, tr {
      display: block;
    }
    thead tr {
      display: none;
    }
    td {
      position: relative;
      padding-left: 50%;
    }
    td::before {
      position: absolute;
      top: 0;
      left: 0;
      width: 45%;
      padding-left: 1em;
      white-space: nowrap;
      font-weight: bold;
    }
    td:nth-of-type(1)::before { content: "Campo"; }
    td:nth-of-type(2)::before { content: "¿Qué indica?"; }
    td:nth-of-type(3)::before { content: "Ejemplo"; }
  }
</style>

## 🧭 Manuales básicos

<details markdown="1">
<summary><i class="fa-solid fa-folder-open"></i> Guía completa de uso de Omeka.net</summary>

### ¿Qué es Omeka.net?

**Omeka.net** es una plataforma en línea para crear sitios web de colecciones digitales y exhibiciones. No requiere instalación ni conocimientos de programación. Es ideal para proyectos en humanidades digitales, archivos, museos o entornos educativos.

### Registrarse y crear un sitio

1. Visita [https://www.omeka.net](https://www.omeka.net)
2. Haz clic en **“Sign Up”**.
3. Elige un plan (el gratuito ofrece 500 MB, suficiente para comenzar).
4. Completa tu registro y confirma el correo.
5. En tu panel, haz clic en **“Create a Site”**.
6. Ingresa:
   - El título del sitio
   - La URL deseada
   - El tema visual (puedes cambiarlo más adelante)

### Añadir ítems (elementos digitales)

1. Ve a **Items > Add an Item**.
2. Llena los campos de metadatos (título, creador, descripción…).
3. En la pestaña **Files**, sube imágenes, PDFs, audio o video.
4. Utiliza el esquema **Dublin Core** para describir los elementos.
5. Guarda tu ítem.

> <i class="fa-solid fa-folder"></i> *Consejo: Describe claramente cada ítem. Esto facilita la navegación y las búsquedas.*

### Organizar con colecciones

1. Ve a **Collections > Add a Collection**.
2. Escribe el nombre y una descripción general.
3. Asocia ítems existentes a esta colección desde la vista de cada ítem.

> <i class="fa-solid fa-link"></i> *Las colecciones agrupan ítems relacionados por tema, época, autor, etc.*

### Crear exhibiciones (exhibits)

1. Ve a **Exhibits > Add an Exhibit**.
2. Escribe el título y una descripción general de la exposición.
3. Agrega páginas (subsecciones) a tu exhibición.
4. En cada página puedes:
   - <i class="fa-solid fa-pen"></i> Escribir texto narrativo.
   - <i class="fa-solid fa-image"></i> Insertar ítems (imágenes, documentos, etc.).
   - <i class="fa-solid fa-puzzle-piece"></i> Usar distintas plantillas de diseño visual.

> <i class="fa-solid fa-palette"></i> *Este módulo permite contar una historia o construir una narrativa curatorial.*

### Personalizar tu sitio

- <i class="fa-solid fa-user"></i> Ve a **Appearance > Themes** para cambiar el aspecto visual.
- <i class="fa-solid fa-tag"></i> Edita el título del sitio, el menú y agrega texto introductorio.
- <i class="fa-solid fa-puzzle-piece"></i> Si tu plan lo permite, activa plugins como **Simple Pages** o **Exhibit Builder**.

### Publicar y compartir

- <i class="fa-solid fa-floppy-disk"></i> Los cambios se guardan automáticamente.
- <i class="fa-solid fa-globe"></i> Tu sitio tendrá una URL como `https://tusitio.omeka.net`
- <i class="fa-solid fa-link"></i> Comparte esta liga para que otros puedan explorar tu proyecto.

### Recomendaciones finales

- <i class="fa-solid fa-book"></i> Usa materiales con licencias libres o Creative Commons.
- <i class="fa-solid fa-clipboard"></i> Sé consistente en el uso de metadatos.
- <i class="fa-solid fa-brain"></i> Planifica la estructura de tu exhibición antes de comenzar.
- <i class="fa-solid fa-handshake"></i> Si trabajas en equipo, asigna roles claros.

</details>

<details markdown="1">
<summary><i class="fa-solid fa-database"></i> Guía completa de clasificación de metadatos (Dublin Core)</summary>

### Básico

| **Campo** | **¿Qué indica?** |
| --- | --- |
| **Título** | Nombre breve que identifica el archivo o el contenido. |
| **Autor o fuente** | Quién creó el archivo o de dónde se obtuvo. |
| **Fecha** | Cuándo se creó o capturó el archivo (día, mes, año). |
| **Ubicación** | Lugar donde se tomó la foto, grabación o se generó el dato. |
| **Tipo de archivo** | Si es audio, imagen, video, texto, etc. |
| **Descripción** | Breve resumen del contenido o contexto del archivo. |
| **Palabras clave** | Temas principales relacionados con el archivo (ej. “patrimonio”, “vida estudiantil”). |
| **Formato** | Extensión del archivo: .jpg, .mp3, .pdf, .docx, etc. |

**Ejemplo:**

- Título: *Escultura del Águila*
- Autor: María López
- Fecha: 12/03/2023
- Ubicación: Plaza Central
- Tipo: Imagen
- Descripción: Escultura ubicada frente a rectoría, símbolo institucional
- Palabras clave: escultura, campus, símbolo
- Formato: .jpg

---

### Dublin Core

- [Especificaciones DCMI Terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/)
- [Element Set (Dublin Core simple)](https://www.dublincore.org/specifications/dublin-core/dces/)
- [Guía para crear metadatos](https://www.dublincore.org/resources/userguide/creating_metadata/)
- [Códigos de lenguas (ISO 639-3)](https://iso639-3.sil.org/code_tables/639/data)

| **Elemento** | **¿Qué poner aquí?** | **Ejemplo** |
| --- | --- | --- |
| **1. Título** | Nombre claro y breve del archivo o recurso | *Entrevista con egresado de 1998* |
| **2. Creador** | Autor(a) de la imagen, grabación, documento, etc. | *Juan Pérez* |
| **3. Tema** | Palabras clave o categorías del contenido | *Vida estudiantil, patrimonio oral* |
| **4. Descripción** | Resumen del contenido o propósito del archivo | *Relato sobre el movimiento estudiantil de los 90* |
| **5. Editor** | Quién publicó o puso en línea el recurso | *Equipo de Patrimonio Digital Tec GDL* |
| **6. Contribuidor** | Otras personas que participaron (entrevistado, editor de audio, etc.) | *María López (edición de audio)* |
| **7. Fecha** | Fecha de creación o captura del archivo | *2024-10-03* |
| **8. Tipo** | Naturaleza del archivo | *Audio*, *Imagen fija*, *Texto digital* |
| **9. Formato** | Formato técnico | *.mp3, .jpg, .pdf, .mp4* |
| **10. Identificador** | Código único para localizar el recurso (puede ser nombre de archivo o URL interna) | *entrevista_egresado1998.mp3* |
| **11. Fuente** | De dónde proviene el archivo (archivo físico, institución, persona) | *Archivo personal de José Ramírez* |
| **12. Idioma** | Lengua principal del contenido | *Español* |
| **13. Relación** | Si está vinculado a otro recurso (por ejemplo, parte de una serie) | *Colección: Testimonios de egresados* |
| **14. Cobertura** | Lugar o periodo relacionado con el contenido | *Campus GDL, 1990–2000* |
| **15. Derechos** | Quién tiene los derechos de uso o si se permite compartir | *CC BY-NC-SA 4.0 – Uso educativo sin fines comerciales* |

**Comentarios:**

- Puedes crear una **plantilla en Excel o Google Sheets** con estos 15 campos como encabezados.
- Cada **fila** será un archivo o recurso.
- Si algún campo no aplica, pon “No aplica”.
- Puedes usar solo los **10 campos más relevantes**: Título, Creador, Tema, Descripción, Fecha, Tipo, Formato, Identificador, Fuente, Derechos.

</details>

<details markdown="1">
<summary><i class="fa-solid fa-map"></i> Guía para crear un mapa sonoro interactivo con MapHub</summary>

### 1. Crear una cuenta en MapHub

- Visita [MapHub](https://maphub.net) y haz clic en **“Sign up”** o **“Iniciar sesión”** en la esquina superior derecha.
- Puedes registrarte con tu correo electrónico o con tu cuenta de Google.
- Si ya tienes cuenta, haz clic en **“Login”** y accede con tus credenciales.

### 2. Crear un nuevo mapa

- Una vez iniciada la sesión, haz clic en **“New Map”**.
- Asigna un nombre y descripción a tu mapa (opcional).
- Elige el estilo de mapa base: por defecto es OpenStreetMap.

### 3. Añadir puntos de interés (marcadores)

- Haz clic en el ícono de marcador (chincheta) en la barra lateral izquierda.
- Coloca el marcador en el lugar deseado (busca la dirección o navega manualmente).
- En la ventana emergente puedes:
  - **Nombrar el marcador**.
  - **Agregar una descripción** del sonido o contexto.
  - **Insertar un audio** mediante un enlace de SoundCloud o Google Drive.

> 🟠 Para Google Drive: asegúrate de que el archivo esté configurado como "compartido públicamente".

### 4. Personalizar los marcadores

- Cambia el ícono, color y tamaño del marcador según el tipo de contenido.
- Usa íconos temáticos relacionados con música, voz, entorno, etc.

### 5. Añadir más puntos

- Repite el proceso para cada nuevo punto que quieras incluir.
- Puedes agregar tantos como desees.

### 6. Guardar y compartir el mapa

- Haz clic en **“Save”**.
- Luego en **“Share”**:
  - Copia el enlace o incrústalo con código HTML.
  - Configura las opciones de privacidad si es necesario.

### 7. Editar el mapa

- Accede a tu cuenta, elige el mapa y haz clic en **“Edit”**.
- Puedes agregar o modificar puntos, descripciones y audios.

### 8. Visualización del mapa

- Los usuarios pueden interactuar con el mapa, hacer clic en los puntos y escuchar los sonidos asociados a cada lugar.

### Consejos adicionales

- 🎧 Usa audios claros y etiquetados adecuadamente.
- 🔗 Verifica que todos los enlaces de audio funcionen correctamente.

> Con esta guía, podrás crear un mapa sonoro atractivo y educativo usando MapHub de manera sencilla.

</details>
