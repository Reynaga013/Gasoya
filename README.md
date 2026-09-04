# GasoYa

App web de un único archivo (sin build, sin backend) para consultar precios de
gasolina/diésel en España: gasolineras cercanas por geolocalización, favoritas
guardadas en el navegador, y búsqueda por municipio/provincia.

## Uso

Abre `index.html` (o `gasoya.html`, es el mismo archivo) directamente con
doble clic — funciona en `file://`. Para que la geolocalización sea fiable
en el móvil, mejor alojarla en https:// (ver siguiente sección). No necesita
`npm install` ni ningún paso de compilación.

## Publicar en GitHub Pages

Ya hay un repositorio git local en esta carpeta (rama `main`, un commit).
Falta solo el push, que necesita tu cuenta de GitHub autenticada:

1. Crea un repositorio vacío en GitHub (por ejemplo `gasoya`) — **sin**
   marcar README, .gitignore ni licencia, para que no choque con lo que
   ya hay aquí.
2. Desde esta misma carpeta, en tu terminal:
   ```
   git remote add origin https://github.com/<tu-usuario>/gasoya.git
   git push -u origin main
   ```
3. En GitHub: Settings → Pages → Source: "Deploy from a branch" → Branch:
   `main` / `(root)` → Save.
4. En un par de minutos, la app estará en
   `https://<tu-usuario>.github.io/gasoya/`.

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
