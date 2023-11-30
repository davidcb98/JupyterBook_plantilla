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


# Roles and directives

Basicamente son funciones. https://myst-parser.readthedocs.io/en/latest/syntax/roles-and-directives.html#syntax-directives

Las **directives** son funciones de varias lineas. Los **roles** son de una línea.








## Cuadros

### Cuadros donde se puede cambiar el título

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

### Cuadros rápidos (no se puede cambiar el título)

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



### Cuadros (usando ::: :::)

::::{important} 
:::{note}

Esto es una nota
:::
::::



:::{admonition} Cuadro de Warning
:class: warning

This is a **warning**
:::



## More directives

````{margin}
Escribimos en el margen !!!!
```{note}
Incluso escribimos notas!!!
```
````



Veamos una hlist:

```{hlist}
    :columns: 3

* Elemento 1
* Elemento 2
* Elemento 3
* Elemento 4
* Elemento 5
* Elemento 6
* Elemento 7
```


### Roles

Veamos un rubric:
```{rubric} This is a rubric (título chulo básicamente)
```

Veamos un centered:
```{centered} Esto es un centered (negrita y centrado)
```

Referencias usando roles: 

Aquí tenemos la página de inicio: {doc}`./index`

Referencias a ecuaciones: {eq}`my_other_label`   

Referencias a figuras: {numref}`Fig. %s <./Mas_cosas#fig-target>`

Referencias a bloques de código {numref}`label_codeblock` (deben de tener tanto :caption: como :name:)


Autor (no se como funciona):

```{sectionauthor} David Castaño Bandín <david.castano@uma.es>
```