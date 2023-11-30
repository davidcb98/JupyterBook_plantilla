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

# Referenciar cosas



Referencia a una sección usando el título: {doc}`./01_00_sec_Code_Blocks_y_Ecuaciones`. Se usa el **nombre del fichero**

    {doc}`./01_00_sec_Code_Blocks_y_Ecuaciones`

Referenciamos una sección {numref}`sec_Code_Blocks_y_Ecuaciones`. Se usa una **label**
    
    `(sec_Code_Blocks_y_Ecuaciones)=`     
    # Code Blocks y Ecuaciones 
    
    {numref}`sec_Code_Blocks_y_Ecuaciones`.

Referencias a ecuaciones: {eq}`my_other_label`  

    {eq}`my_other_label`

Referencias a figuras: {numref}`fig-target`

    {numref}`fig-target`

Referencias a bloques de código {numref}`label_codeblock` (deben de tener tanto :caption: como :name:)

    {numref}`label_codeblock`


## Editar nombre en numref:

Podemos editar el nombre que apare en las numref antes del número. Por ejemplo, podemos pasar de {numref}`fig-target` a {numref}`Figura %s <fig-target>`.

    {numref}`Fig. %s <fig-target>`

Otro ejemplo: {numref}`sec. %s <sec_Code_Blocks_y_Ecuaciones>` en vez de {numref}`sec_Code_Blocks_y_Ecuaciones`.

    {numref}`sec. %s <sec_Code_Blocks_y_Ecuaciones>`
