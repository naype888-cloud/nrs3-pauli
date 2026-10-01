# NRS³ · Pauli

**Two fermions cannot share a state, a shell holds `2n²`, and `2 × 2` holds exactly three
anticommuting spin matrices** — Pauli 1925–27 in Lean 4.

![NRS³ · Pauli](docs/figures/pauli1925.png)

## Results

| Statement | Lean |
|---|---|
| an antisymmetric amplitude vanishes when both particles share a state | `antisymm_apply_self` |
| `ψ ∧ ψ = 0` | `antisymmetrize_self` |
| shells: `∑_{l<n} 2(2l + 1) = 2n²` (2, 8, 18, 32) | `shell_card` |
| `σ_a σ_b + σ_b σ_a = 2δ_ab`, `σ_x σ_y = iσ_z` (by `decide` over `ℤ[i]`) | `sigma_anticomm`, `sigma_mul` |
| no four anticommuting involutions in `Mat₂(ℂ)` | `no_four_anticommuting` |

The shell numbers are capacities, not the lengths of the periods of the table, which also depend
on the energy ordering of subshells.

## In NRS³

NRS³ has three axes; spin has three generators, one per axis, and `2 × 2` has room for exactly
three. A fourth generator, time, forces `4 × 4` (`nrs3-dirac`).

## History

Pauli stated exclusion in 1925, as two electrons never sharing all four quantum numbers, which
explained the closing of the shells; the antisymmetric form came with Heisenberg and Dirac
(1926), and the spin matrices with Pauli (1927). Everything here could have been stated then;
the proofs use modern tools.

## Build

Lean 4 `v4.34.0`, Mathlib `v4.34.0`, nothing else.

```bash
lake exe cache get
lake build
lake env lean Verification/Axioms.lean   # only propext, Classical.choice, Quot.sound
```

Every file: no `sorry`, lines of at most 100 characters, English headers.

## The mosaic

- [NRS and NRS³ — the base theorem](https://github.com/naype888-cloud/nava-robertson-schrodinger)
- [NRS³ · Cramér–Rao](https://github.com/naype888-cloud/nrs3-cramer-rao)
- [NRS³ · Mandelstam–Tamm](https://github.com/naype888-cloud/nrs3-mandelstam-tamm)
- [NRS³ · Penrose](https://github.com/naype888-cloud/nrs3-penrose)
- [NRS³ · Dirac](https://github.com/naype888-cloud/nrs3-dirac)
- **[NRS³ · Pauli](https://github.com/naype888-cloud/nrs3-pauli)** (this one)
- [NRS³ · Poincaré](https://github.com/naype888-cloud/nrs3-poincare)

## License

NRS Noncommercial License 1.0.0, see [`LICENSE`](LICENSE). Author: Eduardo Nava-Hernandez.
