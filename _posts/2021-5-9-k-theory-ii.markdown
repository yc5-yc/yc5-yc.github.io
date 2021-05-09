---
layout: post
title:  "Basics of algebraic K-theory, part II"
date:   2021-05-09
---

<script type="text/javascript"
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

<div style="display:none">
$$
\newcommand{\K}{\mathrm{K}}
\newcommand{\cC}{\mathcal{C}}
\newcommand{\Fun}{\mathrm{Fun}}
\newcommand{\Mor}{\mathrm{Mor}}
\newcommand{\Set}{\mathrm{Set}}
\newcommand{\Map}{\mathrm{Map}}
\renewcommand{\|}{|}
$$
</div>

Last time we defined "exact K-theory" for $$\infty$$-categories with cofibrations, by considering Barwick's $$S_\bullet$$-construction which is the $$\infty$$-categorical version of Waldhausen's construction. In this post we will still analyze the exact sequence structure, but give a more straightforward construction in the setting of exact $$\infty$$-categories.

# Exact ($$\infty$$-)category
To define the Q-construction, Quillen considered the so-called exact categories in his [paper](https://scholar.google.com/scholar?hl=en&as_sdt=0%2C5&q=quillen+higher+algebraic+k+theory&btnG=). Recall that an exact category $$\cC$$ is an additive category with a collection $$\Sigma$$ of short exact sequences $$0\to M'\to M\to M''\to 0$$ ($$M'\to M$$ are called inflations, $$M\to M''$$ are called deflations) such that $$\Sigma$$ contains every canonical exact sequence $$0\to M'\to M'\oplus M''\to M''\to 0$$ and deflations are closed under composition and pullback along any map, inflations are closed under composition and pushout along any map.

This was generalized to an exact $$\infty$$-category in Barwick's [paper](https://arxiv.org/pdf/1301.4725.pdf), but to define it we must first define an additive $$\infty$$-category. In [Gepner-Groth-Nikolaus](https://arxiv.org/pdf/1305.4550.pdf), a preadditive $$\infty$$-category is a pointed $$\infty$$-category admits finite products and finite coproducts such that canonical maps $$X\sqcup Y\to X\times Y$$ are equivalences, we write this as $$X\oplus Y$$. With some machinery from Lurie's [HA](https://www.math.ias.edu/~lurie/papers/HA.pdf) section 2.4.3, we can obtain a fold map $$\nabla: X\oplus X\to X$$ giving the $$\mathbb{E}_\infty$$-monoid structure of any $$X\in \cC$$. And then we define the shear map $$s:X\oplus X\to X\oplus X$$, as the projection map $$pr_1$$ on the first factor and the fold map $$\nabla$$ on the second.

A preadditive $$\infty$$-category $$\cC$$ is defined to be additive if for any $$X\in \cC$$ the shear map $$s:X\oplus X\to X\oplus X$$ gives an equivalence.

Now we list some consequences: an $$\infty$$-category is additive iff its homotopy category is additive; an ordinary category is additive iff its nerve is additive; if an $$\infty$$-category $$\cC$$ is additive, then for any simplicial set $$K$$ we have $$\Fun(K,\cC)$$ additive; any stable $$\infty$$-category is additive (see HA section 1.1.2).

An exact $$\infty$$-category $$\cC$$ is an additive $$\infty$$-category with collections of cofibrations and fibrations such that both $$\cC$$ with cofibrations and $$\cC^{op}$$ with fibrations are $$\infty$$-category with cofibrations, and in the following square with $$f,f'$$ cofibrations and $$g,g'$$ fibrations, it's a pushout square iff it's a pullback square, we call this square ambigressive:

$$
\require{amscd}
\begin{CD}
    X@>f>> Y\\
        @VgVV @VVg'V\\
        Z @>f'>> W
\end{CD}
$$

An exact sequence in an exact category is defined by an ambigressive square:

$$
\require{amscd}
\begin{CD}
    X'@>i>> X\\
        @VVV @VVpV\\
        * @>>> X''
\end{CD}
$$
where $$p$$ is called the cofiber and $$i$$ is called the fiber.

We also record the fact that if $$(\cC,\Sigma)$$ is an exact category, then $$N(\cC)$$ is an exact $$\infty$$-category if we see inflations as cofibrations and deflations as fibrations. Conversely, if $$N(\cC)$$ is exact and we let $$\Sigma$$ as all exact sequences in $$N(\cC)$$, then $$(\cC,\Sigma)$$ is exact.

# The Q-construction
Let $$\cC$$ be an exact $$\infty$$-category. To define the Q-construction $$Q(\cC)$$, we need to define the edgewise subdivision of a simplicial set, which is a little bit annoying to write down. Anyway, for a simplicial set $$X$$, the edgewise subdivision $$\epsilon^*X$$ is a simplicial set given by $$(\epsilon^*X)_n=\Mor(\Delta^{n,op}\star\Delta^n,X)\simeq X_{2n+1}$$ where $$\star$$ refers to join.

The Q-construction $$Q(\cC)$$ is a simplicial set $$\Delta^{op}\to \Set$$ such that $$Q(\cC)_n$$ is the collection of functors $$(\epsilon^*\Delta^n)^{op}\to\cC$$ where the image of any square is ambigressive in $$\cC$$.

It can be proved that $$Q(\cC)$$ is an $$\infty$$-category. To show our final conclusion that $$\K(\cC)\simeq \Omega Q(\cC)$$ as Kan complexes, we need to define an auxiliary simplicial Kan complex $$Q_\bullet(\cC)$$. $$Q_n(\cC)$$ (NOT the $$Q(\cC)_n$$ as before!) is a Kan complex, which is the full subcategory of $$\Map((\epsilon^*\Delta^n)^{op},\cC)^\simeq$$ spanned by elements (which are themselves functors) of $$Q(\cC)_n$$.

Using the machinery of complete Segal space $$Q_\bullet(\cC)$$, one can prove $$\| Q_\bullet(\cC)\|\simeq Q(\cC)$$. So we only need to prove $$\K(\cC)\simeq \Omega\| Q_\bullet(\cC)\|$$: for K-theory space we can invoke Waldhausen's construction $$\mathrm{Gap}_{[\bullet]}(\cC)^\simeq$$ and use the functor $$\Fun(N([2n+1]^{(2)}),\cC)\to\Fun((\epsilon^*\Delta^n)^{op},\cC)$$ as a bridge to connect with the $$Q_\bullet$$-construction, and obtain a simplicial map $$\mathrm{Gap}_{[2n+1]}(\cC)^\simeq\to Q_n(\cC)$$ between Kan complexes. This is an equivalence by the uniqueness of limits in $$\infty$$-categories. Moreover, we should notice $$\|\mathrm{Gap}_{[\bullet]}(\cC)^\simeq\|\simeq\|\mathrm{Gap}_{[2\bullet+1]}(\cC)^\simeq\|$$ to conclude the proof.
