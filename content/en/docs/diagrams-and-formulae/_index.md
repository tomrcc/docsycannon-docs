---
_schema: index
title: Diagrams and Formulae
linkTitle: Diagrams and Formulae
description: How to use Latex and Katex in DocsyCAnnon
weight: 8
categories:
  - Diagrams
  - Formulae
tags:
  - Diagrams
  - Formulae
  - Scientific Notation
  - Chemistry
  - Mathematics
---
## LATE​X support with KaTeXKATE​X

With KaTeXKATE​X support enabled in DocsyCannon, you can include complex mathematical formulae into your web page, either inline or centred on its own line. Since KaTeXKATE​X relies on server side rendering, it produces the same output regardless of your browser or your environment. Some examples below:

The probability of getting \\(k\\) heads when flipping \\(n\\) coins is:

```math
\tag*{(1)} P(E) = {n \choose k} p^k (1-p)^{n-k}
```

*Precipitation of barium sulfate:* \\(\\ce\{SO4^2- + Ba^2+ -&gt; BaSO4 v\}\\)

* Scientific number notation: \\(\\pu\{1.2e3 kJ\}\\) or \\(\\pu\{1.2E3 kJ\}\\) \\
* Divisions: \\(\\pu\{123 kJ/mol\}\\) or \\(\\pu\{123 kJ//mol\}\\)

$\\ce\{x Na(NH4)HPO4 -&gt;\[\\Delta\] (NaPO3)\_x + x NH3 ^ + x H2O\}$

{{< card >}}$\\ce\{Zn^2+ &lt;=&gt;\[+ 2OH-\]\[+ 2H+\] $\\underset\{\\text\{amphoteres Hydroxid\}\}\{\\ce\{Zn(OH)2 v\}\}$ &lt;=&gt;\[+ 2OH-\]\[+ 2H+\] $\\underset\{\\text\{Hydroxozikat\}\}\{\\ce\{\[Zn(OH)4\]^2-\}\}$\}${{< /card >}}

$\\ce\{Zn^2+ &lt;=&gt;\[+ 2OH-\]\[+ 2H+\] $\\underset\{\\text\{amphoteres Hydroxid\}\}\{\\ce\{Zn(OH)2 v\}\}$ &lt;=&gt;\[+ 2OH-\]\[+ 2H+\] $\\underset\{\\text\{Hydroxozikat\}\}\{\\ce\{\[Zn(OH)4\]^2-\}\}$\}$

$\\ce\{Hg^2+ -&gt;\[I-\] $\\underset\{\\mathrm\{red\}\}\{\\ce\{HgI2\}\}$ -&gt;\[I-\] $\\underset\{\\mathrm\{red\}\}\{\\ce\{\[Hg^\{II\}I4\]^2-\}\}$\}$

## Enabling Katex

Uncomment the contents of&nbsp;`params.katex`&nbsp;in the `config.yaml` file. Enabling mhchem enables support of chemical formulae.

```yaml
#  KaTeX support
  katex:
    enable: true  # enable/disable KaTeX support
    mhchem:
      enable: true
    html_dom_element: document.body
    options:
      throwOnError: false
      errorColor: '#CD5C5C'
      delimiters:
        - left: $$
          right: $$
          display: true
        - left: $
          right: $
          display: false
        - left: \(
          right: \)
          display: false
        - left: \[
          right: \]
          display: true
```