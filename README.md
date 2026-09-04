# GasoYa

App web de un único archivo (sin build, sin backend) para consultar precios de
gasolina/diésel en España: gasolineras cercanas por geolocalización, favoritas
guardadas en el navegador, y búsqueda por municipio/provincia.

## Uso

Abre `index.html` (o `gasoya.html`, es el mismo archivo) directamente con
doble clic — funciona en `file://`. Para que la geolocalización sea fiable
en el móvil, mejor alojarla en https:// (ver siguiente sección). No necesita
`npm install` ni ningún paso de compilación.

## Publicada en GitHub Pages

`https://reynaga013.github.io/Gasoya/` — repo `Reynaga013/Gasoya`, rama
`main`. Cada vez que se cambia `gasoya.html`/`index.html` (o los iconos,
`manifest.json`, etc.), el flujo es:

```
git add -A
git commit -m "..."
git push
```

El `push` necesita tu cuenta de GitHub autenticada, así que ese paso
siempre lo ejecutas tú desde tu propia terminal — el resto (editar,
`git add`, `git commit`) puede dejarse hecho de antemano.

## Icono / "Añadir a pantalla de inicio"

`favicon.ico`, `icon-*.png` (16 a 512 px, más una versión "maskable" para
Android) y `manifest.json` viven en esta misma carpeta, junto a
`index.html`/`gasoya.html`. Sirven para que la pestaña del navegador, el
icono de "Instalar app" de Chrome/Edge y "Añadir a pantalla de inicio" de
iOS/Android usen el logo de GasoYa (surtidor blanco + gota verde sobre
degradado azul) en vez del icono genérico. Si se cambia el diseño, hay que
regenerar todos los tamaños a la vez para que no queden descoordinados.

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
