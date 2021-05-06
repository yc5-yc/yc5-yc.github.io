---
layout: post
title:  "Basics of algebraic K-theory, part I"
date:   2021-05-07
---

<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      tex2jax: {
        inlineMath: [['$','$'], ['\\(','\\)']]
      },
      TeX: {
        extensions: ["AMSmath.js", "AMSsymbols.js", "AMScd.js"]
      },
      displayAlign: "center",
      displayIndent: "2em",
    });
  </script>
  <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.1/MathJax.js?config=TeX-MML-AM_CHTML"></script>

<div style="display:none">
$\newcommand{\K}{\mathrm{K}}
\newcommand{\cC}{\mathcal{C}}
\newcommand{\Fun}{\mathrm{Fun}}$
</div>

This series of blog posts are my notes on Mao Zhouhang's [thesis](https://webusers.imj-prg.fr/~zhouhang.mao/M2_memoire.pdf) about various constructions of algebraic K-theory, mainly the $\infty$-categorical ones.

The $\K_0$-group of a ring $R$ is also called the Grothendieck group, it aims to classify finitely generated projective modules over $R$. There are two ways to obtain this group, both build on the isomorphism classes of finitely generated projective $R$-modules: one is by taking the group completion of the abelian monoid obtained from direct sum operation, the other is the underlying free abelian group modulo the relation given by short exact sequences.

The aim is to give constructions of (higher) K-theory spaces in $\infty$-categorical sense. Notice a great advantage of $\infty$-category is that it records (higher) homotopies, so the information of "isomorphisms" ignored in above constructions will be preserved. Furthermore, when considering higher categorical algebra, the two constructions (equivalent in $\K_0$ case) basically use different structures of direct sum operation and exact sequence, this gives us different routes (which are eventually compared in the thesis) to  define the K-theory space. In this post of the series, we will consider the structure build from short exact sequence, namely the $S_\bullet$-construction.

# Cofibrations
Consider a short exact sequence $M'\to M\to M''$, it's enough to just take $M'\to M$, we call this a cofibration. This cofibration, together with $M'\to *$, gives us a triangle which is a cofiber sequence.

We should consider $\infty$-categories with cofibrations when dealing with short exact sequence structure. In a pointed $\infty$-category $\cC$, a collection of cofibration is roughly consisting of all equivalences, all maps of the form $*\to X$, and all new cofibrations obtained from existing cofibrations and arbitrary morphisms via certain pushout squares. Plus that they are closed under composition in $\infty$-categorical sense.

One can thus show that nerve of the additive category of finitely generated $R$-modules is an $\infty$-category with cofibrations given by injections; also the full subcategory of this $\infty$-category spanned by finitely generated projective $R$-modules is with cofibrations given by injections with a projective kernel.

Given a pointed $\infty$-category which admits finite coproducts, we can take the collection of cofibrations to be all maps equivalent to a split map $Y\to X\vee Y$.

# The $\K_0$-group
Let $\cC$ be an $\infty$-category with cofibrations, then $\K_0(\cC)$ is the abelian group with generators given by objects in $\cC$, and for any cofibration $X'\to X$ and the cofiber sequence $X'\to X\to X''$ the relation given by $[X']+[X'']=[X]$.

We shall define the K-theory space as the loop space of certain construction: $\K(\cC)=\Omega L$ with relation $\pi_0\K(\cC)=\pi_1(L)=\K_0(\cC)$ and every $X\in \cC$ gives a loop $[X]\in\Omega L$. The construction $L$ is called Waldhausen's $S_\bullet$-construction, with technicalities in $\infty$-category sense carried out by Barwick.

We shall not go into the technical details of [Barwick's paper](https://arxiv.org/pdf/1204.3607.pdf) here. Instead, we give the explicit construction by Waldhausen.

# Waldhausen's construction
Giving a partially ordered set $P$, we have $P^{(2)}=\{ (i,j)\in P\times P | i\leq j\} $. For an $\infty$-category $\cC$ with cofibrations, we define the $P$-gapped object of $\cC$ as a functor $X:N(P^{(2)})\to \cC$, such that $X(i,i)=*$ and for any $i\leq j\leq k$ in $P$, $X(i,j)\to X(i,k)$ is a cofibration, with the triangle $X(i,j)\to X(i,k) \to X(j,k)$ as a pushout square. Denote $\mathrm{Gap}_P(\cC)$ as the full subcategory of $\Fun(N(P^{(2)}),\cC)$ spanned by $P$-gapped objects.

We then give the construction $S_n(\cC)=\mathrm{Gap}_{[n]}(\cC)^\simeq$, where $(-)^\simeq$ means the subcategory spanned by all objects and all equivalences. Notice that Barwick's construction is necessary in order to give an universal characterization of algebraic $K$-theory, for details please look at Barwick's paper.

# K-theory space
$\K(\cC)$ is the loop space of the geometric realization of $S(\cC)$: $\Omega |S_\bullet(\cC)|$. To conclude this post, we try to give the proof of $\pi_0(\K(\cC))=\K_0(\cC)$.

Notice that $\pi_0(\K(\cC))=\pi_1 | \mathrm{Gap}_{[\bullet]}(\cC)^\simeq | $. We only need to analysis $\mathrm{Gap}_{[m]}(\cC)^\simeq$ for $m\leq 2$: $\mathrm{Gap}_{[0]}(\cC)^\simeq$ is singleton, $\mathrm{Gap}_{[1]}(\cC)^\simeq$ gives objects $X\in \cC$, and the diagram of $\mathrm{Gap}_{[2]}(\cC)^\simeq$ gives cofiber sequences $X'\to X\to X''$ which are 2-cells like $[X]\simeq [X']+[X'']$.
