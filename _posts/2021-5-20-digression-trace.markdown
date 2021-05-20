---
layout: post
title:  "Digression: Cyclotomic trace"
date:   2021-05-20
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
$
\newcommand{\K}{\mathrm{K}}
\newcommand{\cC}{\mathcal{C}}
\newcommand{\cD}{\mathcal{D}}
\newcommand{\cF}{\mathcal{F}}
\newcommand{\cG}{\mathcal{G}}
\newcommand{\cS}{\mathcal{S}}
\newcommand{\cI}{\mathcal{I}}
\newcommand{\Fun}{\mathrm{Fun}}
\newcommand{\Fin}{\mathrm{Fin}}
\newcommand{\Mon}{\mathrm{Mon}}
\newcommand{\Grp}{\mathrm{Grp}}
\newcommand{\Kan}{\mathrm{Kan}}
\newcommand{\Ker}{\mathrm{Ker}}
\newcommand{\Coker}{\mathrm{Coker}}
\newcommand{\TC}{\mathrm{TC}}
\newcommand{\Alg}{\mathrm{Alg}}
\newcommand{\Sp}{\mathrm{Sp}}
\newcommand{\bimod}{\mathrm{bimod}}
\newcommand{\StCat}{\mathrm{StCat}}
\newcommand{\colim}{\mathrm{colim}}
\newcommand{\SqZero}{\mathrm{SqZero}}
\newcommand{\fil}{\mathrm{fil}}
\newcommand{\gr}{\mathrm{gr}}
\newcommand{\Hom}{\mathrm{Hom}}
\newcommand{\Cat}{\mathrm{Cat}}
\newcommand{\NMot}{\mathrm{NMot}}
\newcommand{\map}{\mathrm{map}}
\newcommand{\Perf}{\mathrm{Perf}}
\newcommand{\THH}{\mathrm{THH}}
\newcommand{\CycSp}{\mathrm{CycSp}}
\newcommand{\tr}{\mathrm{tr}}
\renewcommand{\|}{|}
$
</div>

**References:** [Hesselholt-Nikolaus](https://arxiv.org/pdf/1905.08984.pdf) and [Blumberg-Gepner-Tabuada](https://arxiv.org/pdf/1001.2282.pdf)

In this post we give a short construction of the cyclotomic trace map from K to TC, following the survey article of Hesselholt-Nikolaus. The construction relies crucially on results of $\infty$-category of noncommutative motives proved by Blumberg-Gepner-Tabuada.

# Noncommutative motives
Write $$\Cat^{stab}_\infty$$ as the $$\infty$$-category of small stable $$\infty$$-categories and exact functors. The $$\infty$$-category of commutative motives $$\NMot$$ is defined to be the initial $$\infty$$-category with a functor $$z:\Cat^{stab}_\infty$$ satisfying the following properties:

* $\NMot$ is stable

* For every Verdier sequence (i.e. both a fiber sequence and cofiber sequence) in $\Cat^{stab}_\infty$, the image sequence in $\NMot$ is a fiber sequence. This property is called localization.

* The image of Morita equivalences (i.e. become equivalences after idempotent completion, see HTT 4.4.5) in $\Cat^{stab}_\infty$ are equivalences in $\NMot$.

# Nonconnective K-theory and THH
For a small stable $\infty$-category $\cC$, let $\K(\cC)$ be its nonconnective algebraic K-theory spectrum, then by BGT we have an equivalence $\K(\cC)\simeq\map_{\NMot}(z(\Perf_\mathbb{S}),z(\cC))$ where $\Perf_\mathbb{S}$ is the stable $\infty$-category of compact spectra.

Now we turn to the THH side. For a quick introduction to this circle of definitions, see Antieau's [blog post](https://antieau.github.io/2021/04/13/xr003-ktr.html). The definite reference for this subject is [Nikolaus-Scholze](https://arxiv.org/pdf/1707.01799.pdf). Let $\CycSp$ be the $\infty$-category of cyclotomic spectra. We state the fact that THH can be defined as a functor $$\Cat^{stab}_\infty\xrightarrow{\THH}\CycSp$$ and it satisfies the three properties for $$\NMot$$ listed above, the best reference for this is the forthcoming cyclic K-theory paper by Thomas Nikolaus. As a result, we get a unique factorization of THH: $$\Cat^{stab}_\infty\xrightarrow{z}\NMot\xrightarrow{\tr}\CycSp$$ with $$\tr$$ exact. Notice that the definition of $$\TC(\cC)$$ for a stable $$\infty$$-category $$\cC$$: $$\TC(\cC)=\map_\CycSp(\mathbb{S}^{triv},\THH(\cC))$$. Then the induced map of mapping spectra $$\map_\NMot(z(\Perf_\mathbb{S}),z(\cC))\xrightarrow{\tr}\map_\CycSp(\mathbb{S}^{triv},\THH(\cC))$$ is the cyclotomic trace map $$\K(\cC)\xrightarrow{\tr}\TC(\cC)$$.
