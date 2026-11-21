# One-way prime-race windows recur together at positive density

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24411637.svg)](https://doi.org/10.5281/zenodo.24411637)

This result is now maintained in [theta-host-split-inert-race](https://github.com/leecrossley/theta-host-split-inert-race/tree/main/results/theta-race-paired-density). This repository is archived and keeps its releases and DOI.

Assume the generalised Riemann hypothesis (GRH) for the primitive Dirichlet functions in the 547/727 race and its base field, including the Riemann zeta function. Alpöge's announced Dirichlet GRH theorem supplies this input. [Announcement](https://alpo.ge/remark.pdf) [Independent formal checks](https://math.mit.edu/~drew/grh/)

The dyadic 547/727 prime-ideal race has two certified windows. Every doubling gains in the first and every doubling loses in the second. Shift both starting heights by the same multiplicative factor. **A positive lower logarithmic density of shifts preserves both signs throughout both windows.** The separation stays fixed at $`15529862.885`$ in log height. [Proof](PROOF.md)

| Starting heights considered | Guaranteed proportion in log height |
|---|---|
| All intervals of log length $`T`$, uniformly as $`T\to\infty`$ | At least $`2^{-52862}`$ in the lower limit |
| Every finite prefix from the original positive window, for any $`T\gt 0`$ | At least $`2^{-52863}`$ |

Each gain exceeds $`(\log2)/40`$ and each loss exceeds the same magnitude. The first window extends to a completion deadline of $`806.857586\ldots`$ times its starting height. The second extends to $`554.544569\ldots`$ times its own. The proportions are conservative mathematical lower bounds. The actual frequency remains open. [Original windows](https://github.com/leecrossley/theta-race-factor-400/blob/f1773b07a55e76947d4e0c6ab19a112fd91fe6cf/PROOF.md) · [Prior work](PRIOR-WORK.md)

The phase certificate assigns different tolerances to 6,000 individual zero ordinates. The argument allows rational relations, repeated ordinates and additional ordinates at any height on the critical line. A finite collision count proves the prefix bound. A product of triangular functions proves the uniform bound. [Integer partition](evidence/phase-bins.tsv) [Verification output](evidence/check.txt)

## Replay

In a Python 3.10+ virtual environment run

```sh
python -m pip install -r requirements.txt
python check_predecessor.py
python phase_budget.py
python check_budget.py
python check_source.py
```

On x86-64 Linux with Git, curl, tar and zstd, `bash verify-release.sh` checks the hashes, upstream records, two coefficient calculations and five local Lean proofs. With Lean 4.33.1 on PATH and a clean, built Git checkout of Mathlib at commit `0df444a360eaa60ab8c11dca51a86af692955474`, run `bash verify-release.sh /path/to/mathlib4`. An optional second argument gives the local directory of the five upstream records. When the live audit logs change, the script checks archived copies against the published hashes. The phase table columns are the coefficient numerator and bin exponent in the order of the predecessor’s zero brackets. The Fourier and measure arguments are written proofs. [Lean file](PairedDensity.lean) [Hashes](SHA256SUMS) [Replay of the window theorem](https://github.com/leecrossley/theta-race-factor-400/releases/tag/v1.0.0)
