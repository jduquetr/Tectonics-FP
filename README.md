# TectonicsWeb

Re-implementación en navegador (HTML/JS, un solo archivo, sin dependencias) de
[TectonicsFP](https://github.com/freiter/TectonicsFP), software de análisis
estructural geológico originalmente escrito en Borland Delphi 2.

**Demo en vivo:**
`https://jduquetr.github.io/Tectonics-FP/`

## ¿Qué es TectonicsWeb?

TectonicsWeb es una reconstrucción moderna, para navegador, de las herramientas
de análisis de geología estructural de TectonicsFP. No es un port línea por
línea del código Pascal original — es una reimplementación fiel de sus
algoritmos matemáticos (proyección estereográfica equiareal, rotación de
ejes, conteo de densidad, inversión de esfuerzos, estadística de Bingham)
sobre una interfaz web nueva, pensada para poder abrirse con un doble clic o
publicarse como página estática, sin instalar nada.

Permite cargar medidas estructurales de campo (estratificación, foliación,
lineaciones, ejes de pliegue, fallas con estría y sentido de movimiento) y
generar a partir de ellas:

- **Editor de datos** — tabla editable con import/export CSV, tipos de rasgo
  geológico (estratificación, foliación, plano axial, clivaje, eje de
  pliegue, lineación, falla).
- **Stereonet equiareal (Schmidt), hemisferio inferior** — polos de planos,
  círculos máximos, lineaciones, vector medio con estadística tipo Fisher.
- **Diagrama de rosa** — histograma circular de azimuts/direcciones de buzamiento,
  con modo bipolar y ancho de sector ajustable.
- **Contorneo de densidad de polos** — método de círculo de conteo (1% de área)
  y método gaussiano ponderado (tipo Kamb).
- **Inversión de esfuerzos** (método Bott/Angelier) — cálculo del ángulo de
  fluctuación por falla para un tensor de esfuerzo candidato, con auto-ajuste
  por búsqueda en grilla.
- **Estadística de Bingham** — descomposición en autovalores/autovectores de la
  matriz de orientación, para clasificar el tejido estructural como
  agrupamiento, guirnalda o distribución aleatoria.
- **Diedros rectos (método NDA / Angelier-Mechler)** — mapa de compatibilidad
  P/T a partir de planos de falla y sus planos auxiliares.
- **Herramienta de rotación** — restitución estructural de todo el conjunto de
  datos mediante rotación eje/ángulo (p. ej. para desplegar un pliegue).

Todo corre 100% en el navegador; los datos se guardan localmente
(`localStorage`) y nada se envía a ningún servidor.

## ¿Qué es TectonicsFP (el software original)?

[TectonicsFP](https://github.com/freiter/TectonicsFP) es un programa de
escritorio para Windows, escrito en Object Pascal para **Borland Delphi 2** a
finales de los años 90 por Detlef Reimann, orientado al análisis
cuantitativo de datos de geología estructural — la clase de software que
usa un geólogo estructural para procesar e interpretar medidas de campo
(orientación de planos y líneas, y cinemática de fallas) recogidas con
brújula/clinómetro.

Sus capacidades principales incluían:

- Proyección estereográfica (redes de Schmidt/Wulff) de polos, planos y
  lineaciones.
- Diagramas de rosa para datos direccionales.
- Contorneo de densidad de puntos sobre la red estereográfica (conteo por
  círculo y por curva gaussiana).
- Análisis de poblaciones de fallas para reconstrucción de paleoesfuerzos:
  método de inversión de esfuerzos (Angelier/Bott), método de diedros rectos
  (NDA) y diagramas P-T/P-B-T.
- Estadística de orientación mediante análisis de autovalores (Bingham).
- Herramientas de rotación de datos para restauración estructural (p. ej.
  desplegar pliegues antes de analizar la fábrica original).
- Gestión de bases de datos de campo con metadatos (ubicación, litología,
  formación, edad, calidad del dato) y exportación a formatos vectoriales
  (DXF, HPGL) para uso en otros programas de dibujo técnico.

Es un software académico ampliamente citado en trabajos de geología
estructural y tectónica de los años 2000-2010, publicado como código abierto
por su autor. El repositorio original con el código fuente en Delphi está en
[github.com/freiter/TectonicsFP](https://github.com/freiter/TectonicsFP), e
incluye un instalador precompilado para Windows en su
[sección de releases](https://github.com/freiter/TectonicsFP/releases).

## Uso local

Abre `index.html` directamente con doble clic, o sírvelo con cualquier
servidor estático:

```bash
python -m http.server 8000
```

## Licencia

Ver [LICENSE](LICENSE) — misma licencia que el proyecto original TectonicsFP.
