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

<a> id="content-with-notebooks" </a>

# Content with notebooks 

```{contents}
:local:
:depth: 1
```

## MyST markdown

MyST markdown works in Jupyter Notebooks as well. For more information about MyST markdown, check
out [the MyST guide in Jupyter Book](https://jupyterbook.org/content/myst.html),
or see [the MyST markdown documentation](https://myst-parser.readthedocs.io/en/latest/).

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
ax.legend(custom_lines, ['Cold', 'Medium', 'Hot']);
```

There is a lot more that you can do with outputs (such as including interactive outputs)
with your book. For more information about this, see [the Jupyter Book documentation](https://jupyterbook.org)

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

## Ecuaciones

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









