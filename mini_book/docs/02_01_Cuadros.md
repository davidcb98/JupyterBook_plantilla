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

# Cuadros

## Cuadros donde se puede cambiar el título

```{admonition} This is an admonition
This is an admonition
```

```{admonition} This is an admonition class note
    :class: note
This is an admonition class note
```

```{admonition} This is an admonition class important
    :class: important

This is an admonition class important
```

```{admonition} This is an admonition class warning
    :class: warning

This is an admonition class warning
```

```{admonition} This is an admonition class tip
    :class: tip

This is an admonition class tip
```

```{admonition} This is an admonition class tip
    :class: seealso

This is an admonition class tip
```

## Cuadros rápidos (no se puede cambiar el título)

```{note}
This a note (no se puede cambiar el titulo)
```

```{warning}
This is a warning (no se puede cambiar el título)
```

```{tip}
This is a tip (no se puede cambiar el título)
```

```{seealso}
This is a seealso (no se puede cambiar el título)
```

````{note}
The next info should be nested
```{warning}
Here's my **warning** 
```
````



## Cuadros (usando ::: :::)

::::{important} 
:::{note}

Esto es una nota
:::
::::



:::{admonition} Cuadro de Warning
:class: warning

This is a **warning**
:::