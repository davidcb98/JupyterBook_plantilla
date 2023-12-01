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

# Figuras

> Align options: “top”, “middle”, “bottom”, “left”, “center”, or “right”

```{figure} ../_Figuras/Descomp_ortogonal.png
    :scale: 50 %
    :alt: map to buried treasure
    :name: fig-target
    :align: center

This is the caption of the figure (a simple paragraph).
```

Referencia a la figura: {numref}`Fig. %s <fig-target>`



```{figure-md} 
:class: myclass
:name: fig-target-2
<img src="../_Figuras/Descomp_ortogonal.png" 
    alt="decipcion de la imagen" 
    class="bg-primary mb-1" 
    width="200px"
    align="center">

This is a caption in **Markdown**
```

```text
Referencia a la figura: {numref}`Figure %s <fig-target-2>`  (no funciona esta referencia)
```

:::{figure-md} 
    :class: myclass
    :name: fig-target_3
<img src="../_Figuras/Descomp_ortogonal.png" 
    alt="decipcion de la imagen" 
    class="bg-primary mb-1" 
    width="200px"
    align="center">

This is a caption in **Markdown**
:::

```text
Referencia a la figura: {numref}`Figure %s <fig-target_3>` (no funciona esta referencia)
```


![](https://myst-parser.readthedocs.io/en/latest/_static/logo-wide.svg)