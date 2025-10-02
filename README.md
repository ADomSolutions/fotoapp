# 📸 FotoApp

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Pillow](https://img.shields.io/badge/Pillow-Image%20Processing-4B8BBE)](https://python-pillow.org/)
[![OpenCV](https://img.shields.io/badge/OpenCV-Computer%20Vision-5C3EE8)](https://opencv.org/)
[![Matplotlib](https://img.shields.io/badge/Matplotlib-Plotting-0C5A5A)](https://matplotlib.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](./LICENSE)

**FotoApp** es una utilidad de línea de comandos para procesar imágenes con Python:
- Redimensiona una imagen a tamaños estándar de redes sociales (YouTube, Instagram, Twitter, Facebook).
- Ajusta contraste por ecualización de histograma.
- Aplica una batería de **filtros** (Pillow) y guarda los resultados.
- Genera un **boceto** (efecto “sketch”) con OpenCV.

> Proyecto educativo con actitud de herramienta real. Minimalista pero con pegada: corre en consola y guarda salidas útiles.

---

## ✨ Funcionalidades

- **Redimensionar para redes**  
  Mantiene proporción y adapta a presets: `YouTube (1280×720)`, `Instagram (1080×1080)`, `Twitter (1200×675)`, `Facebook (1200×630)`.  
  _Función:_ `redimensionar_imagen(ruta, plataforma)` (usa `Pillow`). :contentReference[oaicite:1]{index=1}

- **Ajustar contraste**  
  Convierte a escala de grises y aplica `equalizeHist` (OpenCV), mostrando comparativa y guardando `contraste_ajustado.png`.  
  _Función:_ `ajustar_contraste(ruta_imagen)`. :contentReference[oaicite:2]{index=2}

- **Aplicar filtros**  
  Soporta: `BLUR, CONTOUR, DETAIL, EDGE_ENHANCE, EDGE_ENHANCE_MORE, EMBOSS, FIND_EDGES, SHARPEN, SMOOTH`.  
  Genera imágenes individuales `imagen_<FILTRO>.png` y una grilla `todos_los_filtros.png`.  
  _Función:_ `aplicar_filtro(ruta_imagen, filtro_elegido)` (Pillow + Matplotlib). :contentReference[oaicite:3]{index=3}

- **Generar boceto (sketch)**  
  Pipeline: gris → invertir → blur gaussiano → división para boceto. Guarda `boceto_generado.png`.  
  _Función:_ `generar_boceto(ruta_imagen, persona=True)` (OpenCV). :contentReference[oaicite:4]{index=4}

- **Menú interactivo en consola**  
  `menu()` guía el flujo. Nota: primero se redimensiona (opción 1); luego se habilitan opciones 2–4. :contentReference[oaicite:5]{index=5}

---

## 🗂️ Salidas esperadas

- `contraste_ajustado.png`  
- `imagen_<FILTRO>.png` (uno por cada filtro)  
- `todos_los_filtros.png` (mosaico comparativo)  
- `boceto_generado.png`  
- La imagen redimensionada se **muestra**; si querés guardarla descomentá la línea `save(...)` en `redimensionar_imagen`. :contentReference[oaicite:6]{index=6}

---

## ⚙️ Instalación

```bash
# 1) Clonar
git clone https://github.com/tuusuario/fotoapp.git
cd fotoapp

# 2) Entorno virtual (opcional, recomendado)
python -m venv .venv
# Linux/Mac
source .venv/bin/activate
# Windows
.venv\Scripts\activate

# 3) Dependencias
pip install -r requirements.txt
