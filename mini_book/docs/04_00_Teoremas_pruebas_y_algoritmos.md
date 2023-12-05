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

# Teoremas, pruebas, algoritmos ...


Infrastructure to support items such as proof and algorithm style formatting is provided by the [sphinx-proof](https://sphinx-proof.readthedocs.io/en/latest/) extension.

Para ver todas las directivas: https://sphinx-proof.readthedocs.io/en/latest/syntax.html#collection-of-directives

## Theorems

```{prf:theorem} Titulo del teorema (opcional)
:label: my-theorem

Esto sería un teorema
```

Referenciamos: {prf:ref}`my-theorem`

## Lemmas

```{prf:lemma} Titulo del lemma (opcional)
:label: my-lemma

Esto sería un lemma
```

Referenciamos: {prf:ref}`my-lemma`

## Corollaries

```{prf:corollary} Titulo del corollary (opcional)
:label: my-corollary

Esto sería un corollary
```

Referenciamos: {prf:ref}`my-corollary`

## Proofs

```{prf:proof} 


Esto sería un proof. No se puede referenciar
```


## Definitions

```{prf:definition} Titulo del definition (opcional)
:label: my-definition

Esto sería un definition
```

Referenciamos: {prf:ref}`my-definition`

## Examples

```{prf:example} Titulo del example (opcional)
:label: my-example

Esto sería un example
```

Referenciamos: {prf:ref}`my-example`

## Axioms

```{prf:axiom} Titulo del axiom (opcional)
:label: my-axiom

Esto sería un axiom
```

Referenciamos: {prf:ref}`my-axiom`

## Algoritms

```{prf:algorithm} Titulo del algoritm (opcional)
:label: my-algorithm

Esto sería un algorithm
```

Referenciamos: {prf:ref}`my-algorithm`

## Conjectures

```{prf:conjecture} Titulo del conjetures (opcional)
:label: my-conjecture

Esto sería un conjetures
```

Referenciamos: {prf:ref}`my-conjecture`


## Criteria

```{prf:criterion} Titulo del criteria (opcional)
:label: my-criteria

Esto sería un criteria
```

Referenciamos: {prf:ref}`my-criteria`

## Observations

```{prf:observation} Titulo del observation (opcional)
:label: my-observation

Esto sería un observation
```

Referenciamos: {prf:ref}`my-observation`

## Properties

```{prf:property} Titulo del property (opcional)
:label: my-property

Esto sería un property
```

Referenciamos: {prf:ref}`my-property`

## Propositions

```{prf:proposition} Titulo del proposition (opcional)
:label: my-proposition

Esto sería un proposition
```

Referenciamos: {prf:ref}`my-proposition`

## Remarks

```{prf:remark} Titulo del remark (opcional)
:label: my-remark

Esto sería un remarks
```

Referenciamos: {prf:ref}`my-remark`
