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


(sec_Code_Blocks)=
# Code cells y code Blocks

```{contents}
:local:
:depth: 1
```

En realidad no es necesario poner este indice local. Ya hay el indice de la izquierda y este te pone en azul los titulos de las secciones.

## Code blocks and outputs

Los code block son un tipo de (directives)[./Roles_and_directives.md].

Jupyter Book will also embed your code blocks and output in your book.
For example, here's some sample Matplotlib code:

```{code-cell} ipython3
from matplotlib import rcParams, cycler
import matplotlib.pyplot as plt
import numpy as np
plt.ion()
```

```{code-cell} ipython3
# Fixing random state for reproducibility
np.random.seed(19680801)

N = 10
data = [np.logspace(0, 1, 100) + np.random.randn(100) + ii for ii in range(N)]
data = np.array(data).T
cmap = plt.cm.coolwarm
rcParams['axes.prop_cycle'] = cycler(color=cmap(np.linspace(0, 1, N)))


from matplotlib.lines import Line2D
custom_lines = [Line2D([0], [0], color=cmap(0.), lw=4),
                Line2D([0], [0], color=cmap(.5), lw=4),
                Line2D([0], [0], color=cmap(1.), lw=4)]

fig, ax = plt.subplots(figsize=(10, 5))
lines = ax.plot(data)
ax.legend(custom_lines, ['Cold', 'Medium', 'Hot'])
```

### Celdas no ejecutables pero numeradas y con formato

```{code-block} python
    :lineno-start: 10  # this is a comment
    : # this is also a comment
    :emphasize-lines: "1, 3"
    :caption: |
    :    This is my
    :    multi-line caption. It is *pretty nifty* ;-)
    :name: label_codeblock

a = 2
print('my 1st line')
print(f'my {a}nd line')
```

### Celdas con salida de error

Prueba de celda que da error

```{code-cell} python
print(val_a)
```

### Celdas con scroll

Veamos una celca con scroll en la salida

```{code-cell} python
    :tags: ["output_scroll"]

for ii in range(40):
    print(f"this is output line {ii}")
```

### Colores en los print

Veamos ahora los colores que podemos poner en los print de python:

```{code-cell} python
text = " XYZ "
formatstring = "\x1b[{}m" + text + "\x1b[m"

print(
    " " * 6
    + " " * len(text)
    + "".join("{:^{}}".format(bg, len(text)) for bg in range(40, 48))
)
for fg in range(30, 38):
    for bold in False, True:
        fg_code = ("1;" if bold else "") + str(fg)
        print(
            " {:>4} ".format(fg_code)
            + formatstring.format(fg_code)
            + "".join(
                formatstring.format(fg_code + ";" + str(bg)) for bg in range(40, 48)
            )
        )
```

## Esconder celdas y salidas

Se hace con una tag:
```
:tag: ["hide-input"]
:tag: ["hide-output"]
:tag: ["hide-cell"]
```

```{code-cell} python
    :tags: ["hide-input"]

import numpy as np
import matplotlib.pyplot as plt
plt.ion()

data = np.random.randn(2, 100)
fig, ax = plt.subplots()
ax.scatter(*data, c=data[1], s=100*np.abs(data[0]));
```

```{code-cell} python
    :tags: ["hide-output"]

import numpy as np
import matplotlib.pyplot as plt
plt.ion()

data = np.random.randn(2, 100)
fig, ax = plt.subplots()
ax.scatter(*data, c=data[1], s=100*np.abs(data[0]));
```

```{code-cell} python
    :tags: ["hide-cell"]

import numpy as np
import matplotlib.pyplot as plt
plt.ion()

data = np.random.randn(2, 100)
fig, ax = plt.subplots()
ax.scatter(*data, c=data[1], s=100*np.abs(data[0]));
```

## Eliminar cerdas o salidas

Se hace con una tag:
```
:tag: ["remove-input"]
:tag: ["remove-output"]
:tag: ["remove-cell"]
```


```{code-cell} python
    :tags: ["remove-input"]

import numpy as np
import matplotlib.pyplot as plt
plt.ion()

data = np.random.randn(2, 100)
fig, ax = plt.subplots()
ax.scatter(*data, c=data[1], s=100*np.abs(data[0]));
```

```{code-cell} python
    :tags: ["remove-output"]

import numpy as np
import matplotlib.pyplot as plt
plt.ion()

data = np.random.randn(2, 100)
fig, ax = plt.subplots()
ax.scatter(*data, c=data[1], s=100*np.abs(data[0]));
```

```{code-cell} python
    :tags: ["remove-cell"]

import numpy as np
import matplotlib.pyplot as plt
plt.ion()

data = np.random.randn(2, 100)
fig, ax = plt.subplots()
ax.scatter(*data, c=data[1], s=100*np.abs(data[0]));
```

## glue para insertar variables en el texto


### "Gluing" variables en el notebook

Tenemos que importar la función `glue()` de la libreria `myst_nb`:

```{code-cell} ipython3
from myst_nb import glue
```

Veamos un ejemplo de como usarlo:
```{code-cell} ipython3
my_variable = "here is some text!"
glue("cool_text", my_variable,  display=False)
```

Para llamarla usamos ``` {glue:}`cool_text` ```: {glue:}`cool_text`


### "Gluing" numeros, plots. math y tablas

```{code-cell} ipython3 
# Simulate some data and bootstrap the mean of the data
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt

n_points = 10000
n_boots = 1000
mean, sd = (3, .2)
data = sd*np.random.randn(n_points) + mean
bootstrap_indices = np.random.randint(0, n_points, n_points*n_boots).reshape((n_boots, n_points))

# Calculate the mean of a bunch of random samples
means = data[bootstrap_indices].mean(0)
# Calculate the 95% confidence interval for the mean
clo, chi = np.percentile(means, [2.5, 97.5])

# Visualize the histogram with the intervals
fig, ax = plt.subplots()
ax.hist(means)
for ln in [clo, chi]:
    ax.axvline(ln, ls='--', c='r')
ax.set_title("Bootstrap distribution and 95% CI")

# And a wider figure to show a timeseries
fig2, ax = plt.subplots(figsize=(6, 2))
ax.plot(np.sort(means), lw=3, c='r')
ax.set_axis_off()


# Store the values in our notebook

glue("boot_mean", means.mean(), display=False) # numero
glue("boot_clo", clo, display=False)           # numero
glue("boot_chi", chi, display=False)           # numero

glue("boot_fig", fig, display=False)           # Plot
glue("sorted_means_fig", fig2, display=False)  # Plot

# Dataframes

bootstrap_subsets = data[bootstrap_indices][:3, :5].T
df = pd.DataFrame(bootstrap_subsets, columns=["first", "second", "third"])
display(df)

glue("df_tbl", df, display=False)
```

### "Pasting" las variables

#### glue:any (sin formato)

Por defecto, al usar `{glue:}` estamos usando `{glue:any}`, que pega la salida 
"encolada" en línea o como bloque, respectivamente, sin formato adicional.

Veamos un ejemplo:
```text
In-line text; {glue:}`boot_mean`, and a figure: {glue:}`boot_fig`.
```

In-line text; {glue:}`boot_mean`, and a figure: {glue:}`boot_fig`.


#### glue:text

El `glue:text` es específico àra textos planos. Veamos un ejemplo:

> ```text
> The mean of the bootstrapped distribution was {glue:text}`boot_mean` (95% confidence interval {glue:text}`boot_clo`/{glue:text}`boot_chi`).
> ```
> The mean of the bootstrapped distribution was {glue:text}`boot_mean` (95% confidence interval {glue:text}`boot_clo`/{glue:text}`boot_chi`).


Podemos darle formato al output, como redondear números. La sintaxis es

- ``` {glue:text}`mykey:formatstring` ```

Por ejemplo:

> ```text
> Media: {glue:text}`boot_mean``
> 
> Media redondeada: {glue:text}`boot_mean:.2f`
> ```
> 
> Media: {glue:text}`boot_mean`
> 
> Media redondeada: {glue:text}`boot_mean:.2f`

#### glue:figure

Sirve para figuras y tablas (dataframes).

Figura:
> ````text
> ```{glue:figure} boot_fig
> :figwidth: 300px
> :name: "fig-boot"
> 
> This is a **caption**, with an embedded `{glue:text}` element: {glue:text}`boot_mean:.2f`!
> ```
> ````
> 
> ```{glue:figure} boot_fig
> :figwidth: 300px
> :name: "fig-boot"
> 
> This is a **caption**, with an embedded `{glue:text}` element: {glue:text}`boot_mean:.2f`!
> ```
> ```text
> Here is a {ref}`reference to the figure <fig-boot>`
> ```
> Here is a {ref}`reference to the figure <fig-boot>`

Dataframe: 
> ````text
> ```{glue:figure} df_tbl
> :figwidth: 300px
> :name: "tbl:df"
> 
> A caption for a pandas table.
> ```
> ````
> 
> ```{glue:figure} df_tbl
> :figwidth: 300px
> :name: "tbl:df"
> 
> A caption for a pandas table.
> ```

#### glue:math

```{code-cell} ipython3
import sympy as sym
f = sym.Function('f')
y = sym.Function('y')
n = sym.symbols(r'\alpha')
f = y(n)-2*y(n-1/sym.pi)-5*y(n-2)
glue("sym_eq", sym.rsolve(f,y(n),[1,4]) ,display=False)
```

>````text
>```{glue:math} sym_eq
>:label: eq-sym
>``
>```` 
>
>```{glue:math} sym_eq
>:label: eq-sym
>```


### "Pasting" en tablas

>````text
>| name                            |       plot                    | mean                      | ci                                                |
>|:-------------------------------:|:-----------------------------:|---------------------------|---------------------------------------------------|
>| histogram and raw text          | {glue:}`boot_fig`             | {glue:}`boot_mean`          | {glue:}`boot_clo`-{glue:}`boot_chi`                   |
>| sorted means and formatted text | {glue:}`sorted_means_fig`     | {glue:text}`boot_mean:.3f` | {glue:text}`boot_clo:.3f`-{glue:text}`boot_chi:.3f` |
>````
>
>| name                            |       plot                    | mean                      | ci                                                |
>|:-------------------------------:|:-----------------------------:|---------------------------|---------------------------------------------------|
>| histogram and raw text          | {glue:}`boot_fig`             | {glue:}`boot_mean`          | {glue:}`boot_clo`-{glue:}`boot_chi`                   |
>| sorted means and formatted text | {glue:}`sorted_means_fig`     | {glue:text}`boot_mean:.3f` | {glue:text}`boot_clo:.3f`-{glue:text}`boot_chi:.3f` |




## Estadisticas de las ejecuciones

```{nb-exec-table}
```








