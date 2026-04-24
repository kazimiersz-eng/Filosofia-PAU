# Filosofia-PAU
# Tabla Comparativa · Historia de la Filosofía (PAU) 🏛️📖

Este proyecto es una tabla interactiva y dinámica diseñada para el estudio y repaso de la Historia de la Filosofía (orientada a la PAU/EBAU). Permite comparar fácilmente los conceptos clave de los principales autores a lo largo de las distintas épocas filosóficas.

## 📖 Sobre el proyecto

La principal ventaja de este proyecto es que **no requiere conocimientos de programación para actualizar los datos**. La web se alimenta directamente y en tiempo real de una hoja de cálculo de Google Sheets. Cualquier cambio realizado en el Excel se reflejará automáticamente en la página web al recargarla.

## ✨ Características Principales

* **Sincronización en tiempo real:** Conectado a Google Sheets a través de su API de visualización (`gviz`).
* **Filtros interactivos:** Botones para mostrar u ocultar columnas de autores específicos (Platón, Tomás de Aquino, Descartes, Locke, Marx, Arendt).
* **Bloques desplegables (Acordeón):** Los grandes bloques temáticos (Ontología, Gnoseología, Ética, etc.) se pueden plegar y desplegar para facilitar la lectura. Incluye botones de "Expandir todo" y "Plegar todo".
* **Diseño visual por épocas:** Código de colores pastel para identificar rápidamente la época de cada autor (Antigua, Medieval, Moderna, Contemporánea).
* **Diseño Responsive:** Preparado para hacer scroll horizontal en pantallas pequeñas sin perder la estructura.

## 🛠️ Cómo editar los datos (Reglas del Excel)

Para que el código web interprete correctamente la estructura de la tabla, debes seguir unas sencillas reglas al rellenar tu documento de Google Sheets:

1.  **Bloques principales (Epígrafes / Letras):**
    Para crear una fila negra desplegable (ej. "A — ONTOLOGÍA"), asegúrate de que **solo la primera celda tenga texto** y las celdas de los autores estén vacías (o contengan guiones `-`, `—`). 
    * *Truco infalible:* Si alguna vez falla la detección automática, simplemente pon el símbolo `>` delante del texto (ej. `> A - ONTOLOGÍA`). El código lo detectará, lo convertirá en un título desplegable y borrará el `>` para que no se vea en la web.

2.  **Principios Fundamentales:**
    Si quieres resaltar una fila entera con un diseño especial (fondo oscuro, texto centrado), comienza el texto de la primera celda con una estrella `★` (ej. `★ PRINCIPIO FUNDAMENTAL`).

3.  **Celdas vacías:**
    Si un autor no tiene teoría sobre un concepto específico, deja la celda vacía o escribe un guion largo `—`. La web lo interpretará automáticamente y mostrará la celda en gris cursiva.

## 🚀 Instalación y Uso

1. No requiere instalación, base de datos ni servidor complejo.
2. Simplemente haz doble clic en el archivo `index.html` (o como hayas nombrado al archivo principal) para abrirlo en cualquier navegador web moderno (Chrome, Firefox, Safari, Edge).
3. Asegúrate de tener conexión a internet, ya que necesita descargar los datos desde Google Sheets.

## 👨‍💻 Detalles Técnicos

* **HTML5 / CSS3:** Para la estructura y el diseño. Vanilla CSS utilizando variables nativas (`:root`) para el manejo de colores.
* **Vanilla JavaScript:** Toda la lógica de obtención de datos (Fetch API), renderizado del DOM, filtrado y colapsado se realiza con JavaScript puro, sin dependencias ni librerías externas (como jQuery o React), lo que garantiza máxima rapidez y compatibilidad.
* **Fuente de datos:** ID del documento configurado directamente en el script (`SHEET_ID`). El documento de Google Sheets debe tener los permisos de lectura configurados en "Cualquier persona con el enlace".
