---
layout: post
title:  "Basics of algebraic K-theory, part III"
date:   2021-05-11
---

<script type="text/x-mathjax-config">
    MathJax.Hub.Config({
      TeX: {
        extensions: ["AMSmath.js", "AMSsymbols.js", "AMScd.js"]
      },
    });
</script>
<script type="text/javascript"
src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

<div style="display:none">
$$
\newcommand{\K}{\mathrm{K}}
\newcommand{\cC}{\mathcal{C}}
\newcommand{\Fun}{\mathrm{Fun}}
\newcommand{\Fin}{\mathrm{Fin}}
\newcommand{\Mon}{\mathrm{Mon}}
\newcommand{\Grp}{\mathrm{Grp}}
\newcommand{\Kan}{\mathrm{Kan}}
\renewcommand{\|}{|}
$$
</div>

In this post we will discuss the structure different from previous two posts, namely the "direct sum structure". Recall that our category with direct sum operation forms an abelian monoid, we will realize this as an $$\mathbb{E}_\infty$$-monoid, and construct the group completion functor of it following Gepner-Groth-Nikolaus ([GGN]). This gives the definition of additive K-theory space. To conclude the whole series, we will say some words on Lurie's comparison theorem of K-theory spaces constructed from the two different structures.

# $$\mathbb{E}_\infty$$-monoid and its group completion
For an $$\infty$$-category $$\cC$$ with finite products, an $$\mathbb{E}_\infty$$-monoid $$M$$ in $$\cC$$ is a functor $$M:N(\Fin_*)\to\cC$$ such that for $$n\geq 0$$, the morphism $$M(\langle n\rangle)\to M(\langle 1\rangle)$$ induced by inert maps makes $$M(\langle n\rangle)$$ as $$n$$-fold power of $$M(\langle 1\rangle)$$. $$\Mon_{\mathbb{E}_\infty}(\cC)$$ is the full subcategory of $$\Fun(N(\Fin_*),\cC)$$ spanned by $$\mathbb{E}_\infty$$-monoids.

Also denote $$M$$ as the underlying object $$M(\langle 1\rangle)$$, then we have the (coherently commutative and associative) multiplication map $$m:M\times M\simeq M(\langle 2\rangle)\to M(\langle 1\rangle)\simeq M$$ induced by $$*\mapsto *,1\mapsto 1, 2\mapsto 1$$.

It's natural to define a full subcategory $$\Grp_{\mathbb{E}_\infty}(\cC)$$ of $$\Mon_{\mathbb{E}_\infty}(\cC)$$ as $$\mathbb{E}_\infty$$-groups. By Proposition 1.1 of [GGN], for an $$\mathbb{E}_\infty$$-monoid $$M$$ in $$\cC$$, we have the following equivalent conditions:

* There is an inverse map $$i:M\to M$$ such that the map $$M\xrightarrow{\Delta}M\times M\xrightarrow{id\times i} M\times M\xrightarrow{m} M$$ is homotopic to identity.

* The underlying object in $$h\cC$$ is a group object.

* The shear map $$s:M\times M\to M\times M$$ is an equivalence.

If $$M$$ satisfies these conditions, then it is called an $$\mathbb{E}_\infty$$-group.

Now in addition we assume that $$\cC$$ is presentable, then by adjoint functor theorem one can prove that the functor $$\Grp_{\mathbb{E}_\infty}(\cC)\hookrightarrow \Mon_{\mathbb{E}_\infty}(\cC)$$ admits a left adjoint $$(-)^{gp}:\Mon_{\mathbb{E}_\infty}(\cC)\to \Grp_{\mathbb{E}_\infty}(\cC)$$, this is called the group completion.

# Additive K-theory
From now on we assume Lurie's definition of symmetric monoidal $$\infty$$-categories, see HA section 2.0.

Let $$\cC$$ be an $$\infty$$-category with finite coproducts, then consider its coCartesian symmetric monoidal structure (see HA section 2.4.3), one can construct a symmetric monoidal category $$\cC^\sqcup$$ which has the underlying space $$\cC$$. By straightening and then taking the core, one gets an $$\mathbb{E}_\infty$$-monoid in the $$\infty$$-category $$\Kan$$. We denote this $$\mathbb{E}_\infty$$-monoid as $$\cC^\simeq$$.

The additive K-theory space $$\K_{add}(\cC)$$ is defined as the underlying space of $$(\cC^\simeq)^{gp}$$.

# Lurie's comparison theorem
We now write something about the proof of Theorem 10 in Lurie's  lecture.

Let $$\cC$$ be an additive $$\infty$$-category, then since it admits finite coproducts, it is also an $$\infty$$-category with cofibrations. Then we have a canonical homotopy equivalence $$\K_{add}(\cC)\to \K(\cC)$$.

We only briefly mention Lurie's proof. Notice that we can see $$\K_{add}(\cC)$$ as $$\Omega \| Y_\bullet\|$$ (we haven't treat this description of group completion in this post) where $$Y_\bullet$$ is a simplicial object in $$\Kan$$ given by $$Y_n=(\cC^\simeq)^n$$. Then $$\K_{add}(\cC)\to\K(\cC)$$ is given by a map $$Y_\bullet\to S_\bullet(\cC)$$ defined as $$(C_1,\ldots,C_n)\mapsto(C_1\to C_1\oplus C_2\to\cdots\to C_1\oplus\cdots\oplus C_n)$$ in degree $$n$$. So we need to show $$\|Y_\bullet\|\to\|S_\bullet(\cC)\|$$ is a homotopy equivalence, these objects are actually $$\mathbb{E}_\infty$$-groups, so we have $$\|Y_\bullet\|\simeq\|Y_\bullet\|^{gp}\simeq\|Y_\bullet^{gp}\|$$ and $$\|S_\bullet(\cC)\|\simeq\|S_\bullet(\cC)\|^{gp}\simeq\|S_\bullet(\cC)^{gp}\|$$ and it's reduced to show for $$n\geq 0$$, $$Y_n^{gp}\to S_n^{gp}$$ is a homotopy equivalence. This can be done by the delicate argument sketched in Lurie's lecture.