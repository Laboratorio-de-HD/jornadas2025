---
title: "Guía práctica de scraping con VS Code"
layout: post
date: 2025-06-13
categories: [recursos, scraping, datos]
tags: [python, scraping, vscode, datos, tutorial]
author: jornadas2025
icon: 🔍
description: Guía paso a paso para realizar scraping web usando Python y Visual Studio Code.
---

# 🔍 Guía práctica paso a paso para hacer *scraping* en VS Code (extracción de datos web)

Esta guía está pensada para principiantes que quieren aprender a recolectar datos desde sitios web de forma automatizada, usando Python desde su computadora con **Visual Studio Code (VS Code)**.

---

## 1. 📚 ¿Qué es el *web scraping*?

El *web scraping* es una técnica para extraer información estructurada de sitios web. Puede ser muy útil para crear bases de datos de:

- Libros, películas, productos, artículos, etc.
- Información de perfiles, foros, redes, enciclopedias.
- Contenido no disponible directamente para descarga masiva.

> Siempre revisa las condiciones de uso del sitio antes de hacer scraping. Hazlo con fines éticos y educativos.

---

## 2. 💻 Requisitos previos

- Tener instalado:
  - [Python](https://www.python.org/)
  - [Visual Studio Code](https://code.visualstudio.com/)
- Tener una carpeta de trabajo en tu equipo
- Instalar paquetes necesarios:

Abre una terminal en VS Code y ejecuta:
```bash
pip install requests beautifulsoup4 pandas
```

También puedes crear un entorno virtual:
```bash
python -m venv .venv
source .venv/bin/activate  # En Mac/Linux
o .venv\Scripts\activate  # En Windows
```

---

## 3. 🌐 Estructura básica del scraping

1. Crea un archivo llamado `scraper.py`
2. Copia este ejemplo:

```python
import requests
from bs4 import BeautifulSoup

url = 'https://ejemplo.com/libros'
headers = {"User-Agent": "Mozilla/5.0"}
respuesta = requests.get(url, headers=headers)

soup = BeautifulSoup(respuesta.text, 'html.parser')

libros = soup.find_all('div', class_='libro')
for libro in libros:
    titulo = libro.find('h2').text
    autor = libro.find('span', class_='autor').text
    print(titulo, '-', autor)
```

---

## 4. 📂 Guardar los datos en un archivo CSV

Agrega al script anterior:

```python
import pandas as pd

datos = []
for libro in libros:
    titulo = libro.find('h2').text
    autor = libro.find('span', class_='autor').text
    datos.append({"titulo": titulo, "autor": autor})

df = pd.DataFrame(datos)
df.to_csv("libros.csv", index=False)
```

> Revisa que el archivo `libros.csv` se cree en tu carpeta del proyecto.

---

## 5. ✅ Buenas prácticas

- Usa `headers` para simular un navegador real:
```python
headers = {"User-Agent": "Mozilla/5.0"}
```
- Agrega pausas con `time.sleep()` entre peticiones para evitar bloquear el sitio
- No sobrecargues servidores ni accedas a sitios que lo prohíben
- Utiliza herramientas como [SelectorGadget](https://selectorgadget.com/) para identificar elementos HTML

---

## 6. 📄 Sitios comúnmente scrapeables para fines educativos

- [Books to Scrape](http://books.toscrape.com/)
- [Quotes to Scrape](http://quotes.toscrape.com/)
- [OpenLibrary](https://openlibrary.org/) *(también tiene API)*

---

## 7. 📚 Recursos para profundizar

- Curso gratuito: *Automate the Boring Stuff with Python*
- Documentación: [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/)
- Libro: *Web Scraping with Python* (O'Reilly)

---

📈 Con esta base, puedes comenzar a construir tus propios scripts de extracción de datos desde cualquier sitio web estructurado, trabajando localmente en VS Code. Si necesitas una plantilla para un sitio específico, puedo ayudarte a crearla.
