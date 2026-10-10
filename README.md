# Sample Geometry Lab

An interactive companion to **MATH 4424 Multivariate Analysis, Chapters 1–4**: data summaries and distances (Ch 1), the matrix tools (Ch 2), sample geometry and random sampling (Ch 3), and the multivariate normal (Ch 4). You drag points, rotate vectors and draw random samples, and every number on the page is recomputed live from what you see.

**▶ Live demo: https://joshrkhoo.github.io/sample-geometry-lab/**

It's one HTML file with no build step and no install. Open `index.html` in a browser, or use the link above.

---

## Demos

### 1.2 From a data matrix to x̄, S and R
Each row of **X** is a point. Drag one and watch x̄, **S** and **R** update. The shaded rectangles from x̄ to each point are the products (x_j1 − x̄₁)(x_j2 − x̄₂). Blue ones add to s₁₂ and orange ones subtract from it. Four preset data sets share the same x̄ and **S** but look nothing alike (AI Exploration 2).

![Data matrix demo](docs/demo-data-dark.gif)

### 1.4 Three rulers: Euclidean, standardised and Mahalanobis
P circles the centre at a fixed Euclidean distance while the standardised and Mahalanobis contours through it reshape. Then the units of x₁ change: the Euclidean distance moves, but the other two don't. The right panel shows the whitened view, where the Mahalanobis ellipse becomes a circle.

![Distance demo](docs/demo-distance-dark.gif)

### 3.1 Rows vs columns: the mean is a projection, correlation is an angle
Drag an observation in the scatter plot (left). The right panel shows the same data as two column vectors in ℝ³. Each **y**ᵢ is projected onto **1**, which gives x̄ᵢ**1**. What's left over is the deviation vector **d**ᵢ, at right angles to **1**. The cosine of the angle between **d**₁ and **d**₂ is r₁₂, and the squared area of the shaded parallelogram is (n−1)²|S|.

![Rows vs columns demo](docs/demo-geometry-dark.gif)

### 3.1 Correlation is the cosine of an angle
This is AI Exploration-1 from the slides. Two centred vectors in ℝ⁵ are swept from θ = 0° (r = 1) through 90° (r = 0) to 180° (r = −1), and the scatter plot follows. A verification table checks that the coordinates sum to zero and computes r by hand.

![Correlation angle demo](docs/demo-angle-dark.gif)

### 3.2 x̄ and S are random too
The app draws repeated samples from N₂(μ, Σ). The sample means bunch up inside the Σ/n contour. The running average of s₁₁ settles on σ₁₁ with divisor n−1, and on (n−1)/n · σ₁₁ with divisor n.

![Random sampling demo](docs/demo-sampling-dark.gif)

### Ch 2: Inside S (spectral decomposition and square-root matrices)
A unit circle is turned into the ellipse of **S** one step at a time: rotate by **P**′, stretch by **Λ**^½, then rotate back by **P**. The right panel shows the same 30 observations centred, standardised (**D**^−½, covariance **R**) and whitened (**S**^−½, covariance **I**).

![Spectral decomposition demo](docs/demo-spectral-dark.gif)

### 3.4 Linear combinations and the Rayleigh quotient
Turn the direction **b** and watch each point's projection onto it. The chart underneath shows **b**′**S****b** swinging between λ₂ and λ₁, with the maximum at the first eigenvector.

![Linear combinations demo](docs/demo-combos-dark.gif)

### 4.1 The bivariate normal and conditioning
A density with χ²₂ probability ellipses. As the slice X₁ = x₁ sweeps across, the conditional density of X₂ slides along the regression line, but its width (σ₂₂(1 − ρ²)) never changes.

![Bivariate normal demo](docs/demo-mvn-dark.gif)

### 4.4–4.5 Checking normality
One observation is dragged across the cloud. Its marginal Q-Q plot still looks fine, but it climbs far above the line in the chi-square plot and gets flagged as a multivariate outlier (d² > χ²₂(0.005)).

![Normality demo](docs/demo-normality-dark.gif)

### 4.6 Box-Cox
λ sweeps across the radiation data from Johnson & Wichern. The histogram and Q-Q plot straighten out as λ approaches the maximum-likelihood λ̂ ≈ 0.28.

![Box-Cox demo](docs/demo-boxcox-dark.gif)

---

## What's in each tab

| Tab | Lecture section | You can… |
|---|---|---|
| **x̄, S and R** | 1.2 | Drag, add or delete points, or edit the data matrix. Switch between divisors n and n−1, rescale x₁ to see that covariance has units and correlation doesn't, and compare the same-summaries data sets |
| **Three distances** | 1.4 | Drag P and compare d_E, d_S and d_M with their contours. Change units, place P along or across the cloud, and load the lecture example (S = diag(4, 1), P = (2, 1)) |
| **Rows vs columns** | 3.1 | Drag 3 observations, rotate the ℝ³ column view, switch between divisors n−1 and n, load textbook Example 3.2 or a degenerate data set |
| **Correlation is an angle** | 3.1 | Set θ and ‖**d**₂‖/‖**d**₁‖ and check r = cos θ by hand (Cauchy–Schwarz gives \|r\| ≤ 1) |
| **Random sampling** | 3.2 | Set n, σ₁, σ₂, ρ and compare simulated E(x̄), Cov(x̄), E(S), E(Sₙ) with theory, with short derivations |
| **Generalized variance** | 3.3 | Shape S and read off \|S\|, tr(S), the eigenvalues and the ellipse area. Includes the three \|S\| = 9 matrices from Example 3.8 and the slide questions (why \|S\| ≥ 0, when \|S\| = 0) |
| **Inside S** | Ch 2 + 3.3 | Spectral decomposition S = PΛP′, S^½ and S^−½, R = D^−½SD^−½, and positive-definiteness tests (eigenvalues, Sylvester) |
| **Linear combinations** | 3.4 | Drag **b** and **c** to see b′x̄, b′Sb and b′Sc. The slide 28 example is editable and computed two ways, with a shift *a* to show that a constant moves the mean but not the variance, and with Ax̄ and ASA′ |
| **Bivariate normal** | 4.1 | Set σ₁, σ₂ and ρ and pick a 50/90/95/99% ellipse, checking coverage against 1000 simulated points. Drag the slice to see X₂ given X₁ next to the marginal |
| **Checking normality** | 4.4–4.5 | Normal, heavy-tailed, skewed, outlier and normal-marginals-only data. You get Q-Q plots with r_Q against the Table 4.2 critical points, a chi-square plot, and a ranking of the largest d². Every point can be dragged |
| **Box-Cox** | 4.6 | Slide λ or click the likelihood curve. You see the histogram and Q-Q plot of x^(λ), ℓ(λ) with λ̂ and an approximate 95% interval, and the radiation data plus three simulated sets with a known answer |

## Key formulas covered

- Ch 1: x̄ = (1/n)Σx_j, s_ik, r_ik = s_ik/√(s_ii s_kk), R = D^−½ S D^−½
- Ch 1 distances: d_E = √((x−y)′(x−y)), d_S = √((x−y)′D⁻¹(x−y)), d_M = √((x−y)′S⁻¹(x−y))
- Mean as a projection: (**y**ᵢ′**1** / **1**′**1**) **1** = x̄ᵢ **1**
- Deviation vectors: **d**ᵢ = **y**ᵢ − x̄ᵢ**1**, with **d**ᵢ′**d**ₖ = (n−1) sᵢₖ and cos θᵢₖ = rᵢₖ
- Sampling: E(X̄) = μ, Cov(X̄) = Σ/n, E(S) = Σ, E(Sₙ) = (n−1)/n · Σ
- Spread: |S| = λ₁λ₂ = (n−1)⁻ᵖ (volume)², tr(S) = λ₁ + λ₂
- Ch 2: S = PΛP′, S^½ = PΛ^½P′, R = D^−½ S D^−½
- Linear combinations: ȳ = b′x̄, s²ᵧ = b′Sb, s_yz = b′Sc, ȳ = Ax̄, Sᵧ = ASA′, λ₂ ≤ b′Sb / b′b ≤ λ₁
- Ch 4: (X−μ)′Σ⁻¹(X−μ) ~ χ²ₚ, X₂ | X₁ = x₁ ~ N(μ₂ + σ₁₂/σ₁₁ (x₁−μ₁), σ₂₂ − σ₁₂²/σ₁₁)
- Ch 4 checks: Q-Q pairs (Φ⁻¹((j−½)/n), x₍ⱼ₎), r_Q, d²ⱼ = (xⱼ−x̄)′S⁻¹(xⱼ−x̄), Box-Cox x^(λ) and ℓ(λ)

## Tech

Plain HTML, CSS and JavaScript, drawn on `<canvas>`. Maths is typeset with [MathJax 3](https://www.mathjax.org/) (SVG output) and fonts come from Google Fonts, so both need an internet connection. Without one, the page still works but shows raw TeX and system fonts. Data in the simulation tabs comes from a seeded random generator, so results are reproducible.

Based on Johnson & Wichern, *Applied Multivariate Statistical Analysis*, as taught in MATH 4424.
