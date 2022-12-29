---
title: Research Porject about Acceleration of the solution of Fractional Diffusion Equations in time
summary: A brief introduction about the topic.
tags:
  - Computational Mathematics
date: '2022-08-27T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''


# links:
#   - icon: twitter
#     icon_pack: fab
#     name: Follow
#     url: https://twitter.com/georgecushen
url_code: ''
url_pdf: ''
url_slides: ''
url_video: ''


# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
#slides: example
---
This research project is under the supervision of Professor Olivier about his new method and algorithms in the numerical solution of time-fractional diffusion equation. Our overall thinking is based on these two papers: [paper1](https://arxiv.org/abs/2106.14146) and [paper2](https://www.cambridge.org/core/journals/communications-in-computational-physics/article/abs/fast-evaluation-of-the-caputo-fractional-derivative-and-its-applications-to-fractional-diffusion-equations/AF5FDC74FD7A010ED0ACD291BB1A92B1). Professor has already accomplished the algorithms in paper1 with a complexity of $O(N_{T}N_{S})$ and has been tested in multiple dimensions in C++. However, the paper2 came up an new algorithms with higher effiency and complexity. The algorithms is accomplished in Matlab.

$$
\partial_t u(x, t)-\nabla \cdot\left(\partial_t^{1-\alpha} \kappa_\alpha \nabla u-\boldsymbol{F} \partial_t^{1-\alpha} u\right)(x, t)=f(x, t), \quad \text { for } x \in \Omega \text { and } 0<t<T
$$

My job was about the topics of optimization of the computing algorithms of the time-fractional diffusion equation. My work was based on the newly proposed more efficient Caputo fractional derivative numerical method for a time-fractional equation using Matlab to implement the algorithm in one and two dimensions. And I convert the Matlab code to C++, integrate it with the original code of the second-order accurate scheme algorithms, and test it. This work has succeeded in reducing the complexity of the code from $O(N_{T}^{2}N_{S})$ to $O(N_{S} \cdot logN_{T})O(\log^{2}N_{T})$ in dimensions 1 and 2 and significantly reduces the space complexity.

However, due to certain reason and time restriction of the project. We only accomplished the code transfer and we trying to improve our merged algorithms in the future.

We are also very curious about the application of this algorithm in the field of financial mathematics and quantitative finance. Many option-related models ultimately boil down to a diffusion equation, which is a partial differential equation. So the two algorithms have a high similarity, for example, by the two numerical methods Monte Carlo or finite differnece.

Diffusion Equation:
$$
\frac{\partial \phi(\mathbf{r}, t)}{\partial t}=\nabla \cdot[D(\phi, \mathbf{r}) \nabla \phi(\mathbf{r}, t)]
$$
Spatial derivatives are replaced by finite differences:
$$
\frac{d f}{d x} \rightarrow \frac{f(x+\Delta x)-f(x-\Delta x)}{2 \Delta x} .
$$
Similarly for time derivatives:
$$
\frac{d Q}{d t} \rightarrow \frac{Q^{n+1}-Q^{n-1}}{2 \Delta t}=F^n
$$
This can immediately be solved for $Q^{n+1}$ :
$$
Q^{n+1}=Q^{n-1} \cdot 2\Delta t F^{n}
$$
Ito's lemma: If there is a Wiener process $X$ and a normally distributed increment $dX$ with mean 0 and variance $dt$, then the function $F(X)$ of the increment can be expressed by a Taylor second-order expansion as
$$
d F=\frac{d F}{d X} d X+\frac{1}{2} \frac{d^2 F}{d X^2} d t
$$
More strictly,
$$
d f\left(t, X_t\right)=\left(\frac{\partial f}{\partial t}+\mu_t \frac{\partial f}{\partial x}+\frac{\sigma_t^2}{2} \frac{\partial^2 f}{\partial x^2}\right) d t+\sigma_t \frac{\partial f}{\partial x} d B_t .
$$


