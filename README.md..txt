Infografía Interactiva de Datos: Producción de Trucha en Perú
Proyecto de visualización de datos académicos enfocado en la gestión técnica y el control de calidad en la producción de trucha en el Perú. Diseñado bajo el Modelo RISEN , la infografía presenta un diseño visualmente limpio en su estado inicial, ocultando las cifras y gráficos complejos, y revelándolos únicamente mediante la interacción del usuario (efecto hover o toque en dispositivos móviles).

Tecnologías utilizadas
HTML5 : Estructura semántica del documento, uso de aria-labelsaccesibilidad y etiquetas <canvas>para la renderización de los gráficos.
CSS3 :
Estilos personalizados con uso avanzado de pseudoelementos ( ::before, ::after) para efectos holográficos, subrayados animados y destellos de partículas.
@propertypara animar la rotación de un degradado cónico (borde holográfico).
backdrop-filterpara efecto glassmorphism en las tarjetas.
Tailwind CSS (v3) : Utilizado vía CDN para utilidades rápidas de espacio, flexbox y tipografía.
JavaScript (vainilla) :
Lógica de interacción para revelar datos y animar contadores numéricos con requestAnimationFramey curvas de aceleración cúbica.
Gestión de eventos diferenciada para hover (escritorio) y click/tap (móvil).
Chart.js (v4) : Biblioteca cargada vía CDN para la renderización de los 5 gráficos estadísticos (Barras, Líneas, Circular/Doughnut, Histograma y Barras Horizontales).
Google Fonts : Tipografías Sora (títulos) y Space Grotesk (cuerpo de texto).
Estructura del Proyecto
El proyecto sigue una arquitectura de archivo único (Single-File) para facilitar su distribución y visualización inmediata sin necesidad de servidores complejos ni procesos de compilación.

├── index.html   # Contiene toda la estructura HTML, estilos CSS y lógica JS.└── README.md    # Este archivo de documentación.
Lógica interna deindex.html
El archivo está dividido en tres bloques principales integrados en el y :<head><body>

<style>(CSS) : Defina las variables del diseño (colores, tipografías), las animaciones de fondo (orbes flotantes), el sistema de diseño de las tarjetas holográficas y las media queries para la respuesta adaptativa (responsividad).
<body>(HTML) : Contiene la capa de fondo animado, el encabezado con<main>) con las 5 tarjetas de datos<article>). Cada tarjeta contiene:
Un contenedor frontal (ícono SVG + título).
Un contenedor oculto (número, descripción, etiqueta del gráfico y ).<canvas>
<script>(JS) : Configura las opciones globales de Chart.js, define los conjuntos de datos y las configuraciones específicas para cada gráfico. Incluye también la función de animación de los contadores y los Event Listeners para controlar la interacción del usuario.
Cómo Visualizar Localmente
Dado que es un archivo HTML estático que consume dependencias externas vía CDN, no requiere instalación de paquetes ( , , etc.).npmyarn

Opción 1: Apertura directa (Recomendado)
Simplemente haz doble clic sobre el archivo y se abrirá en tu navegador web predeterminado (Chrome, Firefox, Edge, Safari).index.html

Opción 2: Usar un servidor local (Para desarrollo)
Si estás realizando modificaciones y deseas evitar problemas de caché o políticas CORS estrictas en algunos navegadores, puedes usar un servidor local.

Con VS Código:

Instale la extensión Live Server .
Haga clic derecho en y seleccione "Abrir con Live Server" .index.html
Con Python (si lo tienes instalado):
Abre una terminal en la carpeta del proyecto y ejecuta:

intento

# Para Python 3
python -m http.server 8000

# Para Python 2
python -m SimpleHTTPServer 8000
Luego abre en tu navegador.http://localhost:8000

Con Node.js (si lo tienes instalado):

intento

npx serve .
Características Interactivas
Revelado por Hover/Toque : Las cifras y gráficos están ocultos hasta que el usuario interactúa con la tarjeta.
Efecto Holográfico : Borde rotante con gradiente cónico y un destello luminoso que barre la tarjeta al activarse.
Contadores animados : Los números grandes se animan desde 0 hasta su valor final con una curva de desaceleración.
Subrayado Explosivo : El título principal del encabezado genera líneas de gradiente superior e inferior al pasar el ratón.
Diseño Adaptable (Responsive) : La parrilla se ajusta automáticamente de 3 columnas a 1 columna en pantallas móviles.
Accesibilidad : Respecto a desactivar animaciones para usuarios que lo solicitan, e incluye etiquetas ARIA.prefers-reduced-motion
Créditos:
Desarrollado para el contexto académico de acuicultura y producción de trucha. Modelo RESUCITADO — Sonia Yamila Suasnabar Centeno. ```