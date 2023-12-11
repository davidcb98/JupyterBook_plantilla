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

```{important}
Including plotly plots in a Jupyter Book page is currently not compatible with the dollarmath syntax extension (mathematical notation written between two “$” characters). If you are trying to include both plotly plots and mathematical notation within the same page, and finding that plotly plots are not being rendered, this may be the cause. Try removing all use of the dollarmath syntax within the page and rebuilding the book.
```

```{code-cell} ipython3
import plotly.io as pio
import plotly.express as px
import plotly.offline as py

df = px.data.iris()
fig = px.scatter(df, x="sepal_width", y="sepal_length", color="species", size="sepal_length")
fig
```


## Bokeh

Puede verse [aquí](https://docs.bokeh.org/en/latest/docs/first_steps.html) la documentación y como instalarlo

```{code-cell} ipython3
from bokeh.plotting import figure, show, output_notebook
output_notebook()

p = figure()
p.circle(data["sepal_width"], data["sepal_length"], fill_color=data["species"], size=data["sepal_length"])
show(p)
```


## ipywidgets

```{code-cell} ipython3
import ipywidgets as widgets
```

```{code-cell} ipython3
widgets.IntSlider(
    value=7,
    min=0,
    max=10,
    step=1,
    description='Test:',
    disabled=False,
    continuous_update=False,
    orientation='horizontal',
    readout=True,
    readout_format='d'
)
```

```{code-cell} ipython3
tab_contents = ['P0', 'P1', 'P2', 'P3', 'P4']
children = [widgets.Text(description=name) for name in tab_contents]
tab = widgets.Tab()
tab.children = children
for ii in range(len(children)):
    tab.set_title(ii, f"tab_{ii}")
tab
```

Pueden verse muchos más widgets [aquí](https://ipywidgets.readthedocs.io/en/latest/examples/Widget%20List.html)