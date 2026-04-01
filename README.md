# PDT-AutoMath: Automated Mathematical Discovery
## *Derive — Discover — Name*

**Pisot Dimensional Theory** | Stephanie Alexander · Baryonix Corp. · 2026

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX)

---

This repository applies the [Omega Institute's AutoMath](https://github.com/the-omega-institute/automath) methodology — *Derive, Discover, Name* — to the polynomial pair at the unique **Pisot boundary** of the family xⁿ = x + 1:

```
P3: x³ − x − 1 = 0   →   ρ = 1.32472  (plastic constant, 3D classical sector)
P4: x⁴ − x − 1 = 0   →   Q = 1.22074  (quartic root,     4D quantum sector)
Lock:  N(ρQ) = −1     →   algebraic unit norm identity (proved)
```

**95 theorems across 10 branches of mathematics**, all derived from these three axioms.

### Comparison with AutoMath

| | AutoMath (Omega Institute) | PDT-AutoMath |
|--|--|--|
| **Seed polynomial** | x² = x + 1 (n=2) | x³=x+1 AND x⁴=x+1 (n=3,4) |
| **Roots** | φ = 1.61803 (golden ratio) | ρ = 1.32472, Q = 1.22074 |
| **Additional axiom** | none | N(ρQ) = −1 (proved) |
| **Compositum degree** | 2 | 12 |
| **Unit group rank** | 1 | 5 (Dirichlet) |
| **Theorems** | ~2,350 (Lean 4) | 95 (Python, 95/95 verified) |
| **Physics predictions** | none | 89 at 0.75% mean error |

The n=2 seed (AutoMath's x²=x+1) is the **special case just below** the Pisot boundary.  
PDT uses the two members **straddling** the boundary — where classical physics meets quantum physics.

---

## The Ten Branches

| Branch | Name | Theorems |
|--------|------|----------|
| I | Core Algebra | 12 |
| II | Norm Theory — The Lock N(ρQ)=−1 | 12 |
| III | Integer Sequences (Padovan, Perrin) | 8 |
| IV | Convergence and Spectral Theory | 11 |
| V | Compositum Structure and Unit Group | 6 |
| VI | Elliptic Curves and L-functions | 9 |
| VII | Dynamics and Substitution Systems | 6 |
| VIII | Arithmetic Geometry | 7 |
| IX | Physics Staircase (coupling constants) | 14 |
| X | Golden Ratio and Fibonacci Connections | 10 |
| **Total** | | **95** |

---

## Usage

**Run in Google Colab — no installation needed:**

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/stalex444/pdt-automath/blob/main/notebooks/PDT_AutoMath.ipynb)

```bash
# Install dependencies
pip install sympy numpy

# Run all 10 branches
python PDT_AutoMath.py

# Run a single branch — set BRANCH = 2 in the CONFIG block at the top
python PDT_AutoMath.py
```

---

## Key Results

```
N(ρ)  = +1   (ρ is a positive-norm unit — classical, Pisot, self-dual)
N(Q)  = −1   (Q is a negative-norm unit — quantum, non-Pisot, anti-self-dual)
N(ρQ) = −1   (the algebraic lock — proved in degree-12 compositum)
```

The unit norm identity N(ρQ) = −1 is not a numerical observation. It is a proved theorem, verifiable in 30 seconds via PARI/GP (see [ratio-unit-norm repository](https://github.com/baryonix/ratio-unit-norm)).

### Selected Theorems

- **I.4**: resultant(P3, P4) = 1 — the polynomials share no root in any extension
- **II.3**: N(ρQ) = −1 — the algebraic lock [**THE CENTRAL RESULT**]
- **III.3**: Per(19) = 209 = gravity staircase floor (15²−15−1=209)
- **III.4**: Perrin primality test verified for all primes up to 31
- **IV.7**: Newton power sums p₁=0, p₂=2, p₃=3 for P3-roots
- **IV.8**: Koide ratio p₂/p₃ = 2/3 (lepton mass ratio from polynomial)
- **IX.1**: α⁻¹ = (ρQ)¹⁵/π² = 137.063 (measured 137.036, error 0.020%)
- **IX.11**: γ_BI = λ₄ρ = 0.2396 (LQG Barbero-Immirzi value 0.2375, error 0.86%)
- **IX.14**: G = 6.6741×10⁻¹¹ from floor 224 + screening correction (error 0.003%)

---

## Physical Predictions

The same two polynomials, with the electron mass as the one dimensional scale, give:

| Quantity | Formula | Predicted | Measured | Error |
|----------|---------|-----------|----------|-------|
| α⁻¹ | (ρQ)¹⁵/π² | 137.063 | 137.036 | 0.020% |
| sin²θ_W | λ₄/χ³ | 0.2311 | 0.2312 | 0.04% |
| Y_p | λ₃ | 0.2451 | 0.2449 | 0.08% |
| γ_BI | λ₄ρ | 0.2396 | 0.2375 | 0.86% |
| G | complete formula | 6.6741×10⁻¹¹ | 6.6743×10⁻¹¹ | 0.003% |

---

## Next Step: Lean 4 Formal Verification

The Omega Institute's AutoMath infrastructure can formally verify these branches in Lean 4.  
The three axioms to add:

```lean
-- P3: the cubic polynomial
def P3 (x : ℝ) : ℝ := x^3 - x - 1

-- P4: the quartic polynomial  
def P4 (x : ℝ) : ℝ := x^4 - x - 1

-- norm_lock: the algebraic unit identity (proved in PARI/GP)
axiom norm_lock : norm (rho * Q) = -1
```

---

## Related Repositories

- [golden-ratio-unit-norm](https://github.com/stalex444/golden-ratio-unit-norm) — PARI/GP proof of N(ρQ)=−1
- [dimensional-origin-Newton](https://github.com/stalex444/dimensional-origin-Newton) — derivation of Newton's constant from the Pisot boundary

## Citation

```bibtex
@software{alexander2026pdt_automath,
  author    = {Alexander, Stephanie},
  title     = {PDT-AutoMath: Automated Mathematical Discovery from the Pisot Boundary},
  year      = {2026},
  publisher = {Zenodo},
  doi       = {10.5281/zenodo.XXXXXXX},
  url       = {https://github.com/stalex444/pdt-automath}
}
```

## License

MIT License — free to use, modify, and distribute with attribution.

---

*"Everything solved itself along the way."*  
*The question was why space has three dimensions. Newton's constant was in the way.*
