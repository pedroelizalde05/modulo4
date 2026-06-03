# Módulo 4 — Artículo distill: Industria de la Bicicleta

Este paquete contiene todo lo necesario para compilar el informe en **Posit Cloud / RStudio**.

## Archivos
- `articulo_bicicletas_distill.Rmd` — el artículo (plantilla distill). **Es el que se compila.**
- `bicicletas.json` — datos cuantitativos estructurados (alimentan figuras y tablas).
- `referencias.bib` — referencias bibliográficas (rinden en APA).
- `apa.csl` — estilo de citación APA.

## Pasos en Posit
1. Subí **los cuatro archivos a la misma carpeta** del proyecto.
2. En la consola, instalá los paquetes (una sola vez):
   ```r
   install.packages(c("distill", "ggplot2", "jsonlite", "knitr", "dplyr", "scales"))
   ```
   > Si aparece *"no existe un paquete llamado distill"*, es porque falta instalarlo: corré la línea de arriba.
3. Abrí `articulo_bicicletas_distill.Rmd` y tocá **Knit**. Se genera el `.html` final (como el de la cátedra).

## Qué editar
- **Autores / afiliación / fecha**: en el encabezado YAML (arriba del `.Rmd`). Ya dejé puesto
  `Instituto de Ingeniería Industrial – Universidad Nacional de Cuyo` y la URL de la facultad.
  Reemplazá los nombres y, si querés, poné una fecha fija.
- **ORCID**: está como `0000-0000-0000-0000` (placeholder). Cambialo si tenés uno real.

## Sintaxis útil (la que pedía la cátedra)
- Tachado: `~~texto~~`
- Resaltado: `<mark>texto</mark>`

## Cómo funciona el flujo de datos
El `.Rmd` lee `bicicletas.json` con `jsonlite::fromJSON()` y de ahí arma las 3 figuras
(ggplot2) y las tablas. Si cambiás un número en el JSON, la figura/tabla se actualiza sola
al volver a compilar. Así el JSON es la "fuente de verdad" del informe.

## Importante (honestidad académica)
Los datos y referencias son reales y verificables, pero las consultoras de mercado **no son
papers revisados por pares**. Si la cátedra exige ~10 artículos académicos, reemplazá o
complementá estas fuentes con papers que bajes de **OpenAlex / Google Académico** sobre:
industria de la bicicleta, caucho natural y *Hevea brasiliensis*, cadenas de suministro y
disrupción marítima. Mantené la misma estructura del JSON y del `.bib`.
