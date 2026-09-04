# GasoYa

App web de un único archivo (sin build, sin backend) para consultar precios de
gasolina/diésel en España: gasolineras cercanas por geolocalización, favoritas
guardadas en el navegador, y búsqueda por municipio/provincia.

## Uso

Abre `gasoya.html` directamente con doble clic (funciona en `file://`), o
súbelo a cualquier hosting estático (GitHub Pages, Firebase Hosting...).
No necesita `npm install` ni ningún paso de compilación.

## Cómo funciona

Consulta en directo la API pública y gratuita del Ministerio para la
Transición Ecológica (MITECO) — sin API key, sin servidor propio:

```
https://sedeaplicaciones.minetur.gob.es/ServiciosRESTCarburantes/PreciosCarburantes/EstacionesTerrestres/
```

Todo el filtrado, cálculo de distancias (Haversine) y almacenamiento de
favoritos ocurre en el navegador del usuario — nada sale de ahí.

## Documentación completa

La documentación detallada (arquitectura, decisiones, bugs encontrados,
hoja de ruta) vive en Obsidian, no aquí:

- `Apps/GasoYa/GasoYa - Documentación y Hoja de Ruta.md`
- `Apps/GasoYa/GasoYa - UI y Apariencia.md`
