# Paper Summary LaTeX Templates

Structured LaTeX templates for paper summaries, designed for use in Overleaf.
Three variants are available — choose the one that matches the paper type.

---

## Templates

| Directory | Best for |
|-----------|----------|
| `general/` | General-purpose summaries |
| `theory/` | Theoretical ML — learning theory, computational geometry |
| `empirical/` | Empirical ML — applied CS, systems, benchmarks |

Each directory is self-contained: `main.tex` + `preamble.tex` + `refs.bib`.
On Overleaf, upload the three files from the relevant directory as a new project.

---

## `theory/` — Learning Theory / Computational Geometry

**Sections**
1. **Formal Setting** — precise definitions of objects, model, and goal
2. **Main Results** — theorems with full quantifiers; upper and lower bounds
3. **Key Assumptions** — one `\begin{assumption}` per assumption, with necessity discussion
4. **Proof Techniques** — high-level strategy, key lemma, and `\proofidea{}`
5. **Comparison to Prior Work** — bound comparison table
6. **Limitations & Open Questions**
7. **Personal Notes**

**Extra packages**: `amssymb`, `tikz` (geometry libraries)

**Extra math macros**

| Macro | Output | Use |
|-------|--------|-----|
| `\Oh`, `\Oht` | $\mathcal{O}$, $\tilde{\mathcal{O}}$ | Big-O, soft-O |
| `\VC(\cH)` | $\mathrm{VC}(\mathcal{H})$ | VC dimension |
| `\Rdim_n(\cH)` | $\mathfrak{R}_n(\mathcal{H})$ | Rademacher complexity |
| `\cN(\cH,\eps,d)` | $\mathcal{N}(\mathcal{H},\varepsilon,d)$ | Covering number |
| `\cH`, `\cF`, `\cX`, `\cY`, `\cD` | $\mathcal{H, F, X, Y, D}$ | Standard calligraphic spaces |
| `\Risk(h)`, `\hRisk_n(h)` | $\mathrm{R}(h)$, $\hat{\mathrm{R}}_n(h)$ | True / empirical risk |
| `\KL(p \| q)` | $\mathrm{KL}(p \| q)$ | KL divergence |
| `\eps` | $\varepsilon$ | Shorthand |
| `\Ind{x > 0}` | $\mathbf{1}[x > 0]$ | Indicator function |
| `\iid` | $\overset{\mathrm{iid}}{\sim}$ | i.i.d. sampling |
| `\Pcl`, `\NP`, `\BPP` | $\mathsf{P, NP, BPP}$ | Complexity classes |
| `\conv(S)`, `\diam(S)`, `\vol(K)` | operators | Geometry |
| `\proofidea{...}` | italic paragraph | Informal proof sketch |

---

## `empirical/` — Empirical ML / Applied CS

**Sections**
1. **Motivation & Problem** — the gap, the research question
2. **Method** — key idea, architecture/algorithm, training objective, implementation details
3. **Experimental Setup** — datasets, baselines, metrics, reproducibility
4. **Results** — main comparison table with `\best{}` / `\rowcolor{rowhl}`
5. **Ablations** — per-component contribution with `\better{}` / `\worse{}` deltas
6. **Limitations & Failure Modes**
7. **Open Questions & Extensions**
8. **Personal Notes**

**Extra packages**: `siunitx`, `pgfplots`, `pgfplotstable`, `listings`, `multirow`, `colortbl`

**Extra macros**

| Macro | Example output | Use |
|-------|---------------|-----|
| `\dataset{ImageNet}` | IMAGENET | Dataset name (small-caps) |
| `\model{ViT-B/16}` | VIT-B/16 | Model name (small-caps) |
| `\baseline{Adam}` | `Adam` | Optimizer / config (monospace) |
| `\metric{Top-1 Acc.}` | *Top-1 Acc.* | Metric name (italic) |
| `\best{82.3}` | **82.3** | Best result in a column |
| `\better{+2.1\%}` | ↑ +2.1% (green) | Improvement over baseline |
| `\worse{-1.4\%}` | ↓ -1.4% (red) | Regression |
| `\num{1234567}` | 1,234,567 | Formatted number (`siunitx`) |
| `\SI{90.2}{\percent}` | 90.2% | Value with units (`siunitx`) |

---

## Shared features (all templates)

**Packages**
- Math: `amsmath`, `amsthm`, `mathtools`
- Layout: `geometry` (1-inch margins), `microtype`, `setspace`
- Tables: `booktabs`, `tabularx`
- Figures: `graphicx`, `subcaption`, `wrapfig`
- Algorithms: `algorithm2e`
- Drawing: `tikz`
- References: `natbib` (numeric), `hyperref`, `cleveref`

**Math macros**
- Number sets: `\R`, `\N`, `\Z`, `\Q`, `\C`
- Probability: `\E`, `\Prob`, `\Var`, `\Cov`
- Delimiters (auto-scaling with `*`): `\norm`, `\abs`, `\inner`, `\ceil`, `\floor`
- Operators: `\argmin`, `\argmax`, `\tr`, `\rank`, `\diag`, `\sign`

**Utility macros**
- `\highlight{text}` — blue text for key claims
- `\TODO{text}` — red bold annotation for gaps

---

## Usage

1. Pick a directory matching the paper type.
2. Open / upload in Overleaf (or compile locally with `pdflatex` + `bibtex`).
3. Edit the metadata block at the top of `main.tex`.
4. Fill in each section. Delete sections that don't apply.
5. Add BibTeX entries to `refs.bib` and cite with `\citep{key}` or `\citet{key}`.
6. Compile `main.tex`.
