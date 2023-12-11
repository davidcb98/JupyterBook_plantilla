---
jupytext:
  text_representation:
    extension: .md
    format_name: myst
    format_version: 0.13
    jupytext_version: 1.15.2
kernelspec:
  display_name: Python 3 (ipykernel)
  language: python
  name: python3
---

> {sub-ref}`today` | {sub-ref}`wordcount-words` words | {sub-ref}`wordcount-minutes` min read


# Visualización interactiva de datos

Descarguemos unos datos para estas pruebas:

```{code-cell} ipython3
import plotly.express as px
data = px.data.iris()
data.head()
```

Las salidas interactivas funcionarán bajo el supuesto de que las salidas que producen tienen HTML autocontenido que funciona sin requerir dependencias externas para cargarse. Veamos unas cuantas formas de haces esto con unas librerías de python.

## Altair

Pueden verse [aquí](https://altair-viz.github.io/getting_started/installation.html#installation) las instrucciones para instalar Altair.

```{code-cell} ipython3
import altair as alt
alt.Chart(data=data).mark_point().encode(
    x="sepal_width",
    y="sepal_length",
    color="species",
    size='sepal_length'
)
```

## Plotly

Puede verse [aquí](https://plotly.com/python/getting-started/#JupyterLab-Support-(Python-3.5+)) la documentación y como instalarlo.

````{important} 
For these plots to show, it may be necessary to load require.js, in your _config.yml:
```{code-block} yaml
sphinx:
  config:
    html_js_files:
    - https://cdnjs.cloudflare.com/ajax/libs/require.js/2.3.4/require.min.js
```
````

