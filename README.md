# 🚲 Falabella Colombia - Web Scraper de Bicicletas

![Python](https://img.shields.io/badge/Python-3.10%2B-blue?style=for-the-badge&logo=python&logoColor=white)
![Selenium](https://img.shields.io/badge/Selenium-4.0%2B-green?style=for-the-badge&logo=selenium&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0%2B-150458?style=for-the-badge&logo=pandas&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

Este proyecto es una herramienta de **Web Scraping y extracción automatizada de datos** desarrollada en Python. Su objetivo es extraer, estructurar y consolidar el catálogo comercial de la categoría de **Bicicletas** en la plataforma e-commerce de **Falabella Colombia**.

---

## 📌 Características Principales

* **Evasión de Bloqueos Anti-Bot (WAF):** Utiliza **Selenium WebDriver en modo Headless** simulando la huella digital y comportamiento de un navegador real, evitando respuestas de bloqueo `HTTP 403 Forbidden`.
* **Extracción Inteligente Dual (Dual-Parsing):**
  * **Estrategia Primaria:** Parseo del objeto global de estado `__NEXT_DATA__` (JSON embebido por el framework React/Next.js).
  * **Estrategia de Respaldo:** Extracción de metadatos de datos estructurados Schema.org (`application/ld+json`).
* **Paginación Automática:** Recorre de forma secuencial las páginas configuradas del catálogo.
* **Procesamiento y Limpieza con Pandas:** Formateo de precios en moneda local ($ COP), extracción de SKU único y eliminación de duplicados reincidentes.
* **Exportación Comercial:** Genera un archivo `.csv` codificado en `UTF-8 con BOM` (`utf-8-sig`) y delimitador de punto y coma (`;`), listo para su importación inmediata en Microsoft Excel o Power BI.

---

## 🛠️ Tecnologías Utilizadas

* **Lenguaje:** Python 3.10+
* **Automatización Web:** `selenium`, `webdriver-manager`
* **Análisis Sintáctico HTML:** `beautifulsoup4`
* **Procesamiento de Datos:** `pandas`
* **Compatibilidad de Entorno:** Google Colab / Linux / Windows / macOS

---

## 📊 Estructura de los Datos Extraídos

El dataset generado en la salida contiene las siguientes columnas:

| Columna | Descripción | Ejemplo |
| :--- | :--- | :--- |
| **Referencia (SKU)** | Identificador único del producto en Falabella | `16849201` |
| **Nombre/Marca** | Marca comercial entre corchetes + Nombre del producto | `[GW] Bicicleta De Montaña All Black Rin 29` |
| **Valor** | Precio formateado en pesos colombianos | `$1.199.900` |
| **Características** | Categoría y número de página de extracción | `Bicicletas - Falabella (Pág 1)` |

---

## 🚀 Instalación y Uso

### Opción 1: En Google Colab (Recomendado)

1. Abre un nuevo cuaderno en [Google Colab](https://colab.research.google.com/).
2. Copia y pega el código del script principal `main.py` en una celda.
3. Ejecuta la celda. El script instalará automáticamente las dependencias de Linux (`google-chrome-stable`), ejecutará la extracción y descargará el archivo `productos_falabella_bicicletas.csv` en tu equipo.

### Opción 2: En Entorno Local (PC)

1. **Clona este repositorio:**
   ```bash
   git clone [https://github.com/tu-usuario/falabella-bicicletas-scraper.git](https://github.com/tu-usuario/falabella-bicicletas-scraper.git)
   cd falabella-bicicletas-scraper
