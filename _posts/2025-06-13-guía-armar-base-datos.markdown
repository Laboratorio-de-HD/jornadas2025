---
layout: post
title:  Guía para armar base de datos
date:   2025-06-04
categories: [resources, HHDD]
---

# 🗃 Guía para crear una base de datos con metadatos Dublin Core

Esta guía te explica paso a paso cómo crear una base de datos en formato `.csv` que pueda usarse en herramientas como **Google Colab**, **VS Code** o **JupyterLab**, utilizando la clasificación estándar de metadatos **Dublin Core**.

---

## 🎯 1. Define el propósito de tu base de datos

Antes de comenzar, responde:

- ¿Qué tipo de datos vas a registrar? (Ej: libros, películas, entrevistas, objetos digitales)
- ¿Para qué se usará esta base? (Análisis, archivo, visualización, etc.)
- ¿Quién la consultará?

> Ejemplo: Una base de datos de novelas de ciencia ficción escritas por mujeres entre 2000 y 2025.

---

## 🧱 2. Diseña la estructura usando Dublin Core

Usa campos del estándar [Dublin Core Metadata Element Set](https://www.dublincore.org/specifications/dublin-core/dces/) como encabezados de tus columnas.

### 📊 Tabla de campos recomendados (Dublin Core simplificado)

<table>
  <thead>
    <tr>
      <th style="padding: 8px 20px; text-align: left;">Campo <code>csv</code></th>
      <th style="padding: 8px 20px; text-align: left;">Descripción</th>
    </tr>
  </thead>
  <tbody>
    <tr><td><code>id</code></td><td>Identificador único por fila (obligatorio)</td></tr>
    <tr><td><code>title</code></td><td>Título del recurso</td></tr>
    <tr><td><code>creator</code></td><td>Autor/a o creador/a</td></tr>
    <tr><td><code>subject</code></td><td>Temas o palabras clave</td></tr>
    <tr><td><code>description</code></td><td>Breve resumen del contenido</td></tr>
    <tr><td><code>publisher</code></td><td>Editorial o entidad responsable</td></tr>
    <tr><td><code>contributor</code></td><td>Otras personas que colaboraron</td></tr>
    <tr><td><code>date</code></td><td>Fecha de publicación o creación</td></tr>
    <tr><td><code>type</code></td><td>Tipo de recurso (libro, artículo, audio


📌 El campo `id` debe ser único para cada línea de datos (`bk001`, `bk002`, etc.).

---

## 📂 3. Crea tu archivo `.csv`

1. Abre Google Sheets, Excel o un editor de texto plano.
2. Usa los encabezados anteriores como la primera fila.
3. Llena cada fila con los datos correspondientes.
4. Guarda el archivo como `mi_base_de_datos.csv`.

### 📘 Ejemplo de contenido `.csv`:

```csv
id,title,creator,date,publisher,language,identifier
bk001,Kindred,Octavia E. Butler,1979,Beacon Press,en,978-0807083697
bk002,La mujer habitada,Gioconda Belli,1988,DASA,es,978-958-05-0372-6
bk003,Los recuerdos del porvenir,Elena Garro,1963,Joaquín Mortiz,es,978-968-27-0123-4
```

---

## 🖥 4. Carga tu base en Google Colab o VS Code

### En Google Colab:

```python
import pandas as pd
from google.colab import files

uploaded = files.upload()
df = pd.read_csv("mi_base_de_datos.csv")
df.head()
```

### En VS Code o Jupyter:

```python
import pandas as pd

df = pd.read_csv("ruta/a/mi_base_de_datos.csv")
print(df.head())
```

---

## 🧹 5. Limpieza y validación de los datos

- Verifica que cada `id` sea único.
- Asegúrate de no dejar columnas clave vacías (`title`, `creator`, `date`).
- Usa formatos consistentes: fecha (`YYYY`), idioma (`es`, `en`), tipo (`Libro`, `Ensayo`, etc.).

---

## 📝 6. Documenta tu base

Acompaña tu archivo `.csv` con un `README.md` que contenga:

- Objetivo del proyecto
- Descripción de las columnas
- Fuente de los datos
- Fecha de elaboración
- Licencia o derechos de uso

---

## 🧾 Plantilla `.csv` de ejemplo

👉 [Descargar plantilla CSV de ejemplo](/jornadas2025/assets/data/plantilla_base_datos.csv)

---

## 📌 Recomendaciones finales

- Usa OpenRefine para depurar y estandarizar los datos.
- Mantén consistencia terminológica y de formato.
- Si planeas escalar, considera una base de datos como SQLite o Airtable.

---

## 🖼️ ¿Cómo agregar audios, imágenes o videos a tu base de datos?

Si quieres enriquecer tu base de datos con archivos multimedia —como imágenes, audios o videos—, puedes hacerlo de varias maneras según el nivel técnico y los objetivos de tu proyecto.

### ✅ Opción 1: Vincular archivos multimedia desde tu archivo `.csv`

Puedes agregar columnas adicionales con enlaces a los recursos multimedia:

| id    | title     | image_url              | audio_url            | video_url            |
|-------|-----------|------------------------|----------------------|----------------------|
| bk001 | Kindred   | assets/images/img1.jpg | assets/audio/01.mp3  | assets/video/clip1.mp4 |

Asegúrate de que los archivos estén disponibles públicamente en tu repositorio, por ejemplo:

```
/assets/images/
assets/audio/
assets/video/
```

También puedes usar URLs externas (como YouTube, SoundCloud, etc.).

#### 🔍 Recomendaciones
- Añade campos como `image_caption`, `audio_transcript`, `video_language`, etc., si deseas más control o accesibilidad.
- Usa nombres de archivo coherentes con los IDs (`img_bk001.jpg`, `audio_bk001.mp3`, etc.).

---

### ✅ Opción 2: Usar plataformas como Omeka o CollectionBuilder

Estas plataformas permiten asociar archivos multimedia a cada ítem descrito con metadatos como Dublin Core.

- **Omeka.net**: Plataforma de exhibición digital para humanidades y archivos. Permite importar metadatos y subir archivos.
- **CollectionBuilder**: Funciona con GitHub Pages y Jekyll. Lee un `.csv`, carga medios desde `/assets/` y genera un sitio navegable.

---

### ✅ Opción 3: Integrar medios en visualizaciones interactivas (Jupyter/Colab o HTML)

Si estás trabajando en Jupyter Notebooks o Google Colab, puedes insertar los medios directamente desde los datos:

```python
from IPython.display import Image, Audio, HTML
Image(filename='assets/images/img1.jpg')
Audio(filename='assets/audio/01.mp3', autoplay=True)
```

También puedes usar HTML en sitios estáticos para incrustar los recursos en páginas personalizadas.

---

### 📁 Estructura de carpetas recomendada

```
/assets/
├── data/
│   └── mi_base.csv
├── images/
│   └── img1.jpg
├── audio/
│   └── 01.mp3
└── video/
    └── clip1.mp4
```

En el `.csv`:
```csv
id,title,image,audio,video
bk001,Kindred,assets/images/img1.jpg,assets/audio/01.mp3,assets/video/clip1.mp4
```

Esto facilitará cargar los medios desde tu base de datos y mantener todo organizado y visible desde GitHub Pages u otras plataformas.


---

