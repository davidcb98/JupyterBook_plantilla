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
myst:
  substitutions:
    key1: "I'm a **substitution**"
    key2: |
      ```{note}
      {{ key1 }}
      ```
---

> {sub-ref}`today` | {sub-ref}`wordcount-words` words | {sub-ref}`wordcount-minutes` min read

# Más cosas



Presentamos primero la linea horizontal, pues la usaremos (pueden ser tres `-` o más):

--------------------------------------------------------------------------------

> this is a quote. this is a quote. this is a quote. this is a quote. this is a quote. this is a quote
>
> this is a quote
>
> this is a quote

--------------------------------------------------------------------------------

Veamos otra forma de hacer cuotas:
```{epigraph}
Here is a cool quotation.

-- Jo the Jovyan
```

## Margin and sidebar

```{sidebar} My sidebar title
My sidebar content
```
If you use a sidebar within your content, the sidebar will stay in-line with your page’s content. However, it will be placed to the right, allowing your content to wrap around it. This prevents the sidebar from breaking up the flow of your content. This is particularly useful if you’ve got tall-and-long blocks of content or images that you would like to provide context to throughout your content.



````{margin}
Escribimos en el margen !!!!
```{note}
Incluso escribimos notas!!!
```
````

## hlist

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

## rubric

Veamos un rubric:
```{rubric} This is a rubric (título chulo básicamente)
```

## Centered

Veamos un centered:
```{centered} Esto es un centered (negrita y centrado)
```

## Sectionauthor

Autor (no se como funciona):

```{sectionauthor} David Castaño Bandín <david.castano@uma.es>
```

## Glossary

Veamos glosarios:
```{glossary}
Term one
  An indented explanation of term 1

A second term
  An indented explanation of term2
```

## Sustitutions

Veamos las sustitution (hay que añadirlas al encabezado de la página)

Sustitution 1: {{ key1 }}

Sustitution 2: {{ key2 }}

--------------------------------------------------------------------------------

You can also define book-level substitution variables with the following configuration:

```markdown
parse:
  myst_substitutions:
    key: value
```

--------------------------------------------------------------------------------
Sustituciones con formato: MyST substitutions use Jinja templates in order to substitute in key / values. This means that you can apply any standard Jinja formatting to your substitutions. For example, you can replace text in your substitutions like so:

The original key1: {{ key1 }}

{{ key1 | replace("a substitution", "the best substitution")}}


## Grids

::::{grid}
:gutter: 4

:::{grid-item}
:outline:
A
:::
:::{grid-item}
:outline:
B
:::
:::{grid-item}
:outline:
C
:::
:::{grid-item}
:outline:
D
:::

::::

--------------------------------------------------------------------------------

::::{grid}

:::{grid-item}
:outline:
:columns: 3
A

A2
:::
:::{grid-item}
:outline:
:columns: 9
B

B2
:::
:::{grid-item}
:outline:
:columns: 6
C

C2
:::
:::{grid-item}
:outline:
:columns: 6
D

D2
:::

::::

--------------------------------------------------------------------------------

::::{grid}
:gutter: 3

:::{grid-item-card} One!
Here's the first card.
:::

:::{grid-item-card} Two!
Here's the second card.
:::

:::{grid-item-card} Three!
Here's the third card.
:::
::::

## Dropdowns

```{dropdown} Here's my dropdown
And here's my dropdown content
```

```{admonition} Click here!
:class: tip, dropdown
Here's what's inside!
```

```{note}
:class: dropdown
The note body will be hidden!
```

## Tab content

````{tab-set}
```{tab-item} Tab 1 title
My first tab
```

```{tab-item} Tab 2 title
My second tab with `some code`!
```
````


`````{tab-set}
````{tab-item} C++
```c++
int main(const int argc, const char **argv) {
  return 0;
}
```
````

````{tab-item} Python
```python
def main():
    return
```
````


````{tab-item} Java
```java
class Main {
    public static void main(String[] args) {
    }
}
```
````

`````


## Table 

```{table} My table title
:name: my-table-ref

| header 1 | header 2 |
|---|---|
| 3 | 4 |
```

Here is {numref}`my-table-ref`