# Lean formalization of LS-based self-tuning regulation

Formalization archive for **LS-Based Self-Tuning Regulation with Unknown Input Gain for Arbitrary Bounded References** by Zhaobo Liu.

**[Read the current manuscript](paper/main.pdf)** · [LaTeX source](paper/main.tex) · [Manuscript ZIP](paper/LS_STR_manuscript-2026-10-24.zip)

Manuscript version: **2026-10-24**. This revision is later than the manuscript snapshot in the proof archive below; its correspondence with the Lean code has not been rechecked.

**[Download the proof archive](https://github.com/liuzhaobo-site/ls-str-lean/releases/download/proofs-2026-10-24/LS_STR_gram_covariance_v2-2026-10-24.zip)** · **[Release and checksum](https://github.com/liuzhaobo-site/ls-str-lean/releases/tag/proofs-2026-10-24)** · [中文说明](README.zh-CN.md)

The ZIP contains the complete Lean source, manuscript snapshot, detailed LaTeX/Lean correspondences, pinned dependency manifests, final audit logs, and reproduction tools. The sources are distributed inside the archive; this repository provides the release entry point.

## Results and scope

The recorded whole-paper run built **913 local and common modules** and checked **3696 registered declarations** against their complete Lean types, theorem status and axiom dependencies. Only `propext`, `Classical.choice` and `Quot.sound` were reported.

Of **31 manuscript results**, **20 are VERIFIED** and **11 retain explicitly accepted literature premises**. The main theorem covers the FIR and ARX branches and concludes almost sure residual energy o(N), regressor energy O(N), bounded average input/output energy, and mean squared tracking error converging to the noise variance. Finite initial histories, the transition/capture applications, the literal 9/32 probability composition, and the tracking equivalences are included.

The author accepts the original Guo (1995) results and Tropp (2011), Lemma 2.1. These are explicit proposition arguments in the relevant Lean types, not locally proved literature results or custom axioms. Their current-paper adaptations and final assembly are proved locally.

The complete registry contains **3606 VERIFIED** and **90 PARTIAL/WEAKENED** records. The latter includes the accepted literature dependencies and historical auxiliary statements with narrower scope. The recorded audit has `kernel_and_axioms_passed: true` while strict `success` and `whole_paper_verified` remain `false`. This distinction is preserved in the distribution; unconditional whole-paper verification is not claimed.

## Reproduction

The archive fixes Lean/Lake **4.24.0**, Mathlib **v4.24.0** at commit `f897ebcf72cd16f89ab4577d0c826cd14afaafc7`, and all transitive Git dependencies.

After extraction, start with `README.md`, `docs/RESULTS.md` and `docs/REPRODUCIBILITY.md` inside the archive. `python3 tools/check_integrity.py` verifies the distributed snapshot and its recorded audit; it does not run Lean. `verify.sh` performs a new full audit after the fixed environment is prepared. Expected strict exit codes and the literature boundary are documented there.

The published ZIP was tested by native extraction, CRC, checksum and relocation checks. Four key source modules and all 31 original complete theorem types and axiom outputs were checked again using the existing pinned toolchain and compiled imports. This was not a new clean-machine installation or another compilation of all 913 modules.

The formalization and correspondence records were developed with Codex and collaborating agents. Correspondence between LaTeX and Lean is a recorded Codex reading review, not a machine proof of LaTeX semantics or an independent human review.

## Integrity and attribution

Archive SHA-256:

```text
902700de0d98ffaf0ffa0705ef9642c5c9fbeb7d6452a7e8de348d1602bd840a
```

The original manuscript and proof source are preserved unchanged. Development caches and trial files are excluded. Third-party attribution and the Apache 2.0 license for the adapted Doob inequality code are included in the ZIP. No blanket license has been assigned to the remaining materials; see `NOTICE.md` inside the archive.
