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

Usa campos del estándar [Dublin Core Metadata Element Set](https://www.dublincore.org/specifications/dublin-core/dces/) como encabezados de tus columnas. Aquí una tabla simplificada:

| Campo `csv`       | Descripción                            |
|------------------|----------------------------------------|
| `id`             | Identificador único por fila (obligatorio) |
| `title`          | Título del recurso                     |
| `creator`        | Autor/a o creador/a                    |
| `subject`        | Temas o palabras clave                 |
| `description`    | Breve resumen del contenido            |
| `publisher`      | Editorial o entidad responsable        |
| `contributor`    | Otras personas que colaboraron         |
| `date`           | Fecha de publicación o creación        |
| `type`           | Tipo de recurso (libro, artículo, audio) |
| `format`         | Formato del archivo o medio            |
| `identifier`     | ID externo (ISBN, DOI, URL, etc.)      |
| `source`         | Fuente de origen                       |
| `language`       | Idioma                                 |
| `relation`       | Relación con otras obras               |
| `coverage`       | Cobertura geográfica o temporal        |
| `rights`         | Derechos de uso o licencia             |

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

