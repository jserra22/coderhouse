# 📄 Fast Slides

Este script de Python, diseñado para ejecutarse en Google Colab, permite subir documentos (PDF, DOCX, PPTX, PNG), extraer su contenido textual, resumirlo automáticamente con Gemini y generar una presentación en PowerPoint con los conceptos clave acompañados de imágenes generadas por IA.

---

## 🚀 Funcionalidades principales

- 📤 **Carga de archivos**: Compatible con `.pdf`, `.docx`, `.pptx`, `.png`.  
- 🧠 **Resumen automático**: Usa Google Gemini para identificar temas principales y estructurarlos como bullet points.  
- 🖼️ **Generación de imágenes**: Cada punto clave se transforma en una imagen ilustrativa gracias a Gemini.  
- 📊 **Creación de presentación**: Se genera una presentación `.pptx` con texto e imágenes lista para exponer.  
- 🧹 **Limpieza automática**: Elimina archivos temporales luego del procesamiento.

---

## 📦 Requisitos

- Python 3.8+
- Google Colab
- Clave de API de Google Gemini (almacenada en `userdata` como `GOOGLE_API_KEY`)

---

## 🔧 Cómo usar

1. Almacenar la API de Gemini como GOOGLE_API_KEY en los secretos de usuario de Colab

1. Subí el archivo a analizar desde Colab.

2. El script detecta el tipo de archivo y extrae el texto.

3. Se genera un resumen estructurado y puntos clave usando Gemini.

4. Se crean imágenes representativas de los conceptos clave.

5. Se genera y descarga automáticamente una presentación PowerPoint con el contenido.

---

## 📁 Tipos de archivo soportados

| Tipo | Método de extracción |
|------|----------------------|
| PDF  | `PyPDF2` + `zlib` (para textos comprimidos) |
| DOCX | `python-docx` |
| PPTX | `python-pptx` |
| PNG  | `pytesseract` (OCR) |
| DOC  | ❌ No soportado (se recomienda convertir a .docx) |

## ⚠️ Notas

- Las imágenes generadas pueden demorar algunos segundos dependiendo del rendimiento de la API.
- Actualmente se generan hasta 4 imágenes por resumen.
- Se requiere una clave válida de API de Google para usar Gemini.
