# TectonicsWeb

Re-implementación en navegador (HTML/JS, un solo archivo, sin dependencias) de
[TectonicsFP](https://github.com/freiter/TectonicsFP), software de análisis
estructural geológico originalmente escrito en Borland Delphi 2.

**Demo en vivo:** _(se completa tras activar GitHub Pages — ver abajo)_
`https://<tu-usuario>.github.io/TectonicsWeb/`

## Funcionalidad

- Editor de datos estructurales (planos, líneas, fallas) con import/export CSV
- Stereonet equiareal (Schmidt), hemisferio inferior — polos, círculos máximos, lineaciones, vector medio
- Diagrama de rosa
- Contorneo de densidad de polos (círculo de conteo / gaussiano tipo Kamb)
- Inversión de esfuerzos (método Bott/Angelier) con auto-ajuste
- Estadística de Bingham (autovectores) y diedros rectos (método NDA)
- Herramienta de rotación de conjunto de datos (restauración estructural)

Todo corre 100% en el navegador; los datos se guardan en `localStorage`, no se
envía nada a ningún servidor.

## Uso local

Abre `index.html` directamente con doble clic, o sírvelo con cualquier
servidor estático:

```bash
python -m http.server 8000
```

## Licencia

Ver [LICENSE](LICENSE) — misma licencia que el proyecto original TectonicsFP.
