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



```{figure-md} fig-target-2
:class: myclass
<img src="../_Figuras/Descomp_ortogonal.png" 
    alt="decipcion de la imagen" 
    class="bg-primary mb-1" 
    width="200px"
    align="center">

This is a caption in **Markdown**
```


Referencia a la figura: {numref}`Fig. %s <fig-target-2>` 



![](https://myst-parser.readthedocs.io/en/latest/_static/logo-wide.svg)