# Lean formalization of LS-based self-tuning regulation

Formalization archive for **LS-Based Self-Tuning Regulation with Unknown Input Gain for Arbitrary Bounded References** by Zhaobo Liu.

**[Read the current manuscript](paper/main.pdf)** · [LaTeX source](paper/main.tex) · [Manuscript ZIP](paper/LS_STR_manuscript-2026-10-24.zip)

Manuscript version: **2026-10-24**. This revision is later than the manuscript snapshot in the proof archive below; its correspondence with the Lean code has not been rechecked.

**[Download the proof archive](https://github.com/liuzhaobo-site/ls-str-lean/releases/download/proofs-2026-10-24/LS_STR_gram_covariance_v2-2026-10-24.zip)** · **[Release and checksum](https://github.com/liuzhaobo-site/ls-str-lean/releases/tag/proofs-2026-10-24)** · [中文说明](README.zh-CN.md)

The ZIP contains the complete Lean source, manuscript snapshot, detailed LaTeX/Lean correspondences, pinned dependency manifests, final audit logs, and reproduction tools. The sources are distributed inside the archive; this repository provides the release entry point.

## Results and scope

The recorded whole-paper run built **930 local and common modules** and checked **3778 registered declarations** against their complete Lean types, theorem status and axiom dependencies. Only `propext`, `Classical.choice` and `Quot.sound` were reported.

All **31 manuscript results in the archived snapshot are VERIFIED**, with no external Guo/Tropp premise. The needed LS error bound and bounded-matrix conditional probability comparison are proved locally and supplied inside the main theorem. The proof covers FIR and ARX, finite initial histories, transition/capture, the 9/32 probability composition, and the four stability and tracking conclusions.

Across the complete registry, **3776 entries are VERIFIED** and **2 unused historical sharp Tropp conditional helpers remain PARTIAL/WEAKENED**. No original manuscript result depends on them. The full historical-registry command retains strict `success: false` and `whole_paper_verified: false`, while the actual kernel and axiom audit passed. The requested scope of all 31 original results and both needed inputs passes separately.

The old local interfaces had an incorrect logarithm convention and an omitted measure condition. These formalization defects were repaired; the archived manuscript was not modified. This revision proves only the literature consequences actually needed by the archived manuscript, not the entire Guo or Tropp publications.

## Reproduction

The archive fixes Lean/Lake **4.24.0**, Mathlib **v4.24.0** at commit `f897ebcf72cd16f89ab4577d0c826cd14afaafc7`, and all transitive Git dependencies.

After extraction, start with `README.md`, `docs/RESULTS.md` and `docs/REPRODUCIBILITY.md` inside the archive. `python3 tools/check_integrity.py` verifies the distributed snapshot and its recorded audit; it does not run Lean. `verify.sh` performs a new full audit after the fixed environment is prepared. Expected strict exit codes and the literature boundary are documented there.

The published ZIP was tested by native extraction, CRC, checksum and relocation checks. Four key source modules and all 31 original complete theorem types and axiom outputs were checked again using the existing pinned toolchain and compiled imports. This was not a new clean-machine installation or another compilation of all 930 modules.

The formalization and correspondence records were developed with Codex and collaborating agents. Correspondence between LaTeX and Lean is a recorded Codex reading review, not a machine proof of LaTeX semantics or an independent human review.

## Integrity and attribution

Archive SHA-256:

```text
5bd973c28c7bf57170e36f5619b87300f51eeeb693fdcecbf6a1974e8551f04a
```

The audited manuscript snapshot and proof sources are preserved byte for byte in the ZIP. Development caches and trial files are excluded. Third-party attribution and the Apache 2.0 license for the adapted Doob inequality code are included in the ZIP. No blanket license has been assigned to the remaining materials; see `NOTICE.md` inside the archive.
