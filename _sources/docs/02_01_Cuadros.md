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

# Cuadros (admonitions)

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

```text
Esto es para escribir texto plano. Es decir, no se renderizan 
los comandos estilo {numref}`Figure %s <fig-target_3>`
```

> Quote block
>
> Y vemos que puede ser de varias líneas



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

Para entornos donde no se reconoce la sintaxis 
    ``` 
puede usarse la sintaxis
    :::



::::{important} 
:::{note}

Esto es una nota
:::
::::



:::{admonition} Cuadro de Warning
:class: warning

This is a **warning**
:::

## Cuadros con html

A drawback of admonition syntax is that it will not render in interfaces that do not support this syntax (e.g., GitHub). If you’d like to use admonitions that are defined purely with HTML, MyST can parse them via the html_admonitions extension. 

<div class="admonition note" name="html-admonition" style="background: lightgreen; padding: 10px">
<p class="title">This is the **title**</p>
This is the *content*
</div>

During the Sphinx render, both the class and name attributes will be used by Sphinx, but any other attributes like style will be discarded.

There can be no empty lines in the block, otherwise they will be read as two separate blocks. If you want to use multiple paragraphs then they can be enclosed in `<p>`:

<div class="admonition note">
<p>Paragraph 1</p>
<p>Paragraph 2</p>
</div>


<div class="admonition">
<p>Some **content**</p>
  <div class="admonition tip">
  <div class="title">A *title*</div>
  <p>Paragraph 1</p>
  <p>Paragraph 2</p>
  </div>
</div>