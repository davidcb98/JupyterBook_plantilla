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


# Ecuaciones

\begin{equation} 
    f(x) = x^2 
\end{equation} 

$$
    w_{t+1} = (1 + r_{t+1}) s(w_t) + y_{t+1}
$$ (my_other_label)

A link to a dollar math block: {eq}`my_other_label`

```{math} 
    :label: euler
        e^{i\pi} + 1 = 0
```

Refereciemos la ec. de euler {eq}`euler`.

```{math}
    :label: label_align
        \begin{align}
        y    & =  ax^2 + bx + c \\
        f(x) & =  x^2 + 2xy + y^2 
        \end{align}
```

Refereciemos la ec. {eq}`label_align`.

$$
    \begin{aligned}
    y    & =  ax^2 + bx + c \\
    f(x) & =  x^2 + 2xy + y^2 
    \end{aligned}
$$ (label_align_dolar)

Refereciemos la ec. {eq}`label_align_dolar`.

```{math}
    :label: label_1
        (a + b)^2  &=  (a + b)(a + b) \\
                   &=  a^2 + 2ab + b^2
```
Refereciemos la ec. {eq}`label_1`.









