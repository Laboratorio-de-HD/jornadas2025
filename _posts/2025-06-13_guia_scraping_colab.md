---
title: "Guía práctica de scraping con Google Colab"
layout: post
date: 2025-06-13
categories: [recursos, scraping, datos]
tags: [python, scraping, google-colab, datos, tutorial]
author: Nat R.
icon: 📄
description: Aprende paso a paso a hacer scraping con Python desde Google Colab sin instalar nada en tu computadora.
---

# 📄 Guía sencilla para hacer scraping en Google Colab

Esta guía te mostrará cómo extraer datos de una página web usando Python directamente desde **Google Colab**, sin necesidad de instalar nada en tu computadora.

---

## 1. 💡 ¿Qué es Google Colab?

Google Colab es una herramienta gratuita que te permite programar en Python desde el navegador. Es ideal para comenzar proyectos de scraping sin preocuparte por instalaciones.

👉 Solo necesitas una cuenta de Google y acceso a internet: [https://colab.research.google.com](https://colab.research.google.com)

---

## 2. 🧪 Crea tu primer cuaderno (notebook)

1. Entra a [colab.research.google.com](https://colab.research.google.com)
2. Da clic en **Archivo > Nuevo cuaderno**
3. Cámbiale el nombre a algo como `scraping_basico`

---

## 3. 📦 Instala las bibliotecas necesarias

En la primera celda, ejecuta:

```python
!pip install requests beautifulsoup4 pandas
```

---

## 4. 🌐 Código básico de scraping

Pega este código en una nueva celda:

```python
import requests
from bs4 import BeautifulSoup
import pandas as pd

url = 'http://books.toscrape.com/catalogue/page-1.html'
headers = {"User-Agent": "Mozilla/5.0"}
respuesta = requests.get(url, headers=headers)
soup = BeautifulSoup(respuesta.text, 'html.parser')

libros = soup.find_all('article', class_='product_pod')
datos = []

for libro in libros:
    titulo = libro.h3.a['title']
    precio = libro.find('p', class_='price_color').text
    disponibilidad = libro.find('p', class_='instock availability').text.strip()
    datos.append({"titulo": titulo, "precio": precio, "disponibilidad": disponibilidad})

# Crear un DataFrame
pd.DataFrame(datos)
```

Esto mostrará una tabla con los libros extraídos de la primera página.

---

## 5. 💾 Guardar los datos en un archivo CSV

Agrega esta celda:

```python
df = pd.DataFrame(datos)
df.to_csv('libros.csv', index=False)
```

Luego, para descargar el archivo:

```python
from google.colab import files
files.download('libros.csv')
```

---

## 6. ✅ Buenas prácticas

- Usa siempre `headers` para evitar bloqueos.
- No hagas muchas peticiones muy rápido (puedes usar `time.sleep(1)` entre páginas).
- Practica con sitios diseñados para scraping:
  - [Books to Scrape](http://books.toscrape.com/)
  - [Quotes to Scrape](http://quotes.toscrape.com/)

---

## 7. 🎯 ¿Y luego qué?

- Puedes practicar con más páginas del mismo sitio.
- Intentar extraer más campos (como calificación o enlaces de imagen).
- Usar bucles para recorrer varias páginas.
