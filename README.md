# MOGOPS · Meta‑Ontological Generative Optimization of Phase Space

This repository contains the **MOGOPS‑THO Unified Framework v2.7**, a formal, equation‑driven model for civilizational collapse prediction, recovery analysis, and sacred geography assessment. The framework integrates **268 equations**, a **Core‑24 simulation kernel**, **six collapse modes**, and **24 pre‑registered falsification patterns** into an executable specification ready for simulation, calibration, and empirical testing.

---

## 🔭 What is MOGOPS‑THO?

**MOGOPS‑THO v2.7** is not a poetic metaphor or a speculative philosophy—it is a **formally specified, computationally tractable grammar** for analyzing civilizational systems. It treats a civilization as a **dissipative sacred‑memory system** whose survival depends on the synchronisation of its energy, water, food, administrative ledgers, ritual cohesion, trade networks, craft transmission, and sacred geography.

The framework’s core insight is succinctly captured in its axiom:

> *Collapse begins when reality updates faster than the civilization can rewrite its ledger.*

Rather than predicting collapse from stress alone, the model measures how well a civilization’s **feedback and correction loops** are functioning. A stressed civilization with intact feedback systems can adapt; a civilization with degraded correction capacity will fail even under moderate perturbations.

---

## 📚 Core Components

| Component | Description |
|-----------|-------------|
| **Core‑24 Active Kernel** | The minimal set of 24 equations that run the MVP simulator, governing energy, extraction, water, climate, ledgers, networks, legitimacy, rebellion, memory, and master risk. |
| **Extended Equations (241–268)** | Additional active equations that complete the core kernel, including Plasticity Reserve (PR), Effective LTD, Trust Battery decay, Resentment Potential Energy (RPE), Decapitation Vulnerability Index (DVI), and the Disease Impact submodel. |
| **Six Collapse Modes** | A probabilistic fingerprint vector \([C_I, C_II, C_III, C_IV, C_V, C_VI]\) covering rigid boundary failure, resentment reservoir, decapitation, hydraulic drift, polytope shrink, and survivor adaptation. |
| **Sacred Geography Protocol** | A pre‑registered, null‑model‑protected methodology for evaluating geometric patterns. Geometry alone can never elevate a claim above “candidate relation” without independent non‑geometric evidence. |
| **Falsification Dashboard** | A built‑in test suite with survival controls, randomised null cases, ablation tests, sensitivity ranking, and holdout validation to prevent overfitting and ensure predictive discipline. |
| **Case Presets** | Pre‑parameterised configurations for the Maya, Mexica (Aztec), Tawantinsuyu (Inca), Caral‑Supe, Olmec, and Teotihuacan, ready for simulation. |

---

## ⚙️ Repository Structure

```
MOGOPS/
├── README.md                           # This file
└── MOGOPS-THO/
    ├── MOGOPS-THO-v2.7 (Framework).md  # Complete 268‑equation specification
    └── v2.7-Shortcoming-Report.md      # Independent technical review (Issues 49–68) + v2.8 roadmap
```

---

## 🧠 Key Concepts

### The Master Risk Equation

Risk is computed as a **ratio of damage load to absorption capacity**:

```
Risk = (CSP^ + LTD_eff^ + EPE^ + MA^ + NFR^) /
       (NSE^ + LCC^ + RR^ + MPS^ + PR^ + TB^ + ε)
```

Each term is normalised to [0,1], and the denominator includes an epsilon term for numerical stability.

### The Terminal Condition

A civilization is considered **terminal** when all three of the following hold simultaneously:

- `Risk > 1`
- `LTD_eff > 0.35`
- `PR < 0.1`

### The Fold Catastrophe Detector

A discontinuous transition (fold catastrophe) is signalled when:

```
FoldScore = [ΔLTD > 0.2] + [ΔPR < -0.1] + [ΔTB < -0.2] + [ΔRR < -0.15] ≥ 3
```

---

## 🏛️ Indigenous & Non‑Western Protocol

All case studies in the framework are required to comply with a strict ethical and methodological protocol:

1. Use **local polity names** and categories where attested.
2. **Distinguish governance morphologies** (empire, confederacy, city‑state, sacred network, collective).
3. **Separate archaeological evidence** from colonial chronicles.
4. **Acknowledge living cultural continuity** where present.
5. **Avoid evolutionary ladder language**.
6. **Flag externally imposed categories** with `[externally_imposed]`.
7. **Do not apply collapse framing to living cultures.**

---

## 🧪 Getting Started (Implementation Blueprint)

The reference implementation follows this Python package structure:

```
mogops_tho_v2_7/
├── core/
│   ├── state.py
│   ├── equations.py
│   ├── normalization.py
│   ├── risk.py
│   ├── foldscore.py
│   └── collapse_modes.py
├── presets/
│   ├── maya.json
│   ├── aztec.json
│   ├── inca.json
│   ├── caral.json
│   ├── olmec.json
│   └── teotihuacan.json
├── data/
│   ├── case_template.json
│   └── timeseries_template.csv
├── tests/
│   ├── test_equations.py
│   ├── test_risk.py
│   └── test_foldscore.py
└── outputs/
    ├── dashboards/
    └── runs/
```

The core computation functions include:

- `normalize(x, method)` – percentile, min‑max, or expert prior scaling
- `compute_ltd_eff(vec, G)` – Mahalanobis LTD from the 5‑component vector
- `compute_pr(…)` – Plasticity Reserve (critical early‑warning metric)
- `update_trust_battery(…)` – clamped TB update with explicit decay
- `compute_master_risk(…)` – Eq. 254
- `compute_foldscore(…)` – Eq. 256
- `classify_collapse_modes(…)` – returns the 6‑mode fingerprint vector

All variables are normalised to [0,1] and carry provenance metadata (source, confidence, observer class, temporal/spatial resolution). Confidence is **never multiplied into the core risk equation**; it is reserved for uncertainty bands in Monte Carlo runs (minimum 1,000 iterations).

---

## 📊 Case Presets (Six Civilizations)

| Preset | Morphology | NSE | LCC | RR | PR | TB | Primary Collapse Mode |
|--------|------------|-----|-----|----|----|----|----------------------|
| Maya Classic | Ritual City‑State Network | 0.55 | 0.70 | 0.45 | 0.35 | 0.50 | C_IV + C_V |
| Mexica Triple Alliance | Militaristic Tribute Engine | 0.70 | 0.75 | 0.25 | 0.20 | 0.25 | C_II |
| Tawantinsuyu (Inca) | Andean Logistical Bureaucracy | 0.75 | 0.80 | 0.55 | 0.08 | 0.35 | C_III |
| Caral‑Supe | Sacred Coordination Node | 0.60 | 0.45 | 0.70 | 0.65 | 0.80 | C_VI |
| Olmec Heartland | Symbolic Unification Field | 0.50 | 0.40 | 0.60 | 0.55 | 0.75 | C_VI |
| Teotihuacan | Urban Redistribution Hub | 0.80 | 0.65 | 0.30 | 0.25 | 0.55 | C_I + C_V |

---

## 🔬 24 Pre‑Registered Falsification Patterns

The framework includes 24 testable predictions, each with an explicit falsifier and a support level (S0‑S4). Examples:

| ID | Pattern | Falsifier | Support |
|----|---------|-----------|---------|
| P01 | Plasticity‑Collapse Inversion: in hydraulic empires, PR falls below 0.15 before LTD exceeds 0.35 | A hydraulic empire where LTD > 0.35 precedes PR < 0.15 | S2 |
| P02 | Ritual Bandwidth as LTD Accelerator: when RB > 0.7 and LTD_ritual > 0.3, LTD_eff grows 3× faster | High‑RB case with ≤1× growth | S1 |
| P03 | Trust Battery Hysteresis: TB recovers at 0.2× the speed it decays | TB recovery > 0.5× decay within 2 generations | S2 |
| P04 | The 0.35–0.1 Double Threshold: no empire survived with LTD_eff > 0.35 and PR < 0.1 for >5 phase‑years | Any polity sustaining both >5 years without collapse | S1 |
| P13 | Disease Impact = Specialist Mortality × Ritual Contradiction: with SMR > 0.3 and RitualContradiction = 1, collapse risk doubles | High SMR + RitualContradiction = 1 without collapse acceleration | S1 |
| P14 | Heresy as Adaptive Reset: destabilising when LE < 0.2, helpful when LE > 0.4 | Heresy at LE > 0.4 that increases collapse risk | S0 (hypothesis) |
| P24 | Coherence Phase Lock: survivors maintain phase‑lock between RUC, RR and LCC growth | Survivor with one slow variable lagging > 0.3 phase‑units for >15 years | S2 |

The full set of 24 patterns is detailed in the main framework document (Part III).

---

## ✅ Anti‑Overfitting Controls

Before any pattern or equation can be promoted to Active status, the model must pass five controls:

1. **Survival dataset** – at least 10 collapse cases + 10 survival/transformation cases.
2. **Randomised null cases** – synthetic civilizations with shuffled variables.
3. **Ablation tests** – removal of each core variable; if removal has no effect, the variable is demoted.
4. **Sensitivity ranking** – perturb all variables by ±10% to identify the most and least influential terms.
5. **Control cases** – the model must **not** flag Haudenosaunee, Venice, Byzantium (selected periods), or Japan as terminal.

---

## 📄 v2.7 Shortcoming Report & v2.8 Roadmap

An independent technical review (May 2026) identified **20 specific shortcomings** in v2.7, classified as Critical (3), High (10), and Medium (7). The most critical issues are:

- **#49** Double‑counting of LTD_eff in the master risk equation.
- **#50** Recursive definition of PR (Pattern Rigidity) that creates a circular dependency.
- **#51** Epsilon dominance when the risk denominator approaches zero.

The full issue table and proposed v2.8 repairs are documented in [`v2.7-Shortcoming-Report.md`](https://github.com/TaoishTechy/MOGOPS/blob/main/MOGOPS-THO/v2.7-Shortcoming-Report.md). The roadmap prioritises empirical validation over further theoretical expansion, with the next milestone being a working simulator tested against six collapse cases and five survival controls.

---

## 🧠 Neurophenomenology Appendix (N1–N72)

The framework originally contained 72 equations (169–240) on DMT, psilocybin and mescaline pharmacokinetics. These have been **explicitly firewalled** into a separate appendix with the following status:

> **⚠️ Poetic / Appendix status – NOT part of the civilizational collapse simulator.**  
> *Inclusion is symbolic / neurocognitive only. These equations are NOT instructions for synthesis, extraction, dosing or use of any substance.*

The appendix remains in the repository as a historical and theoretical artefact, but it is **not** referenced in the Core‑24 kernel or the falsification dashboard.

---

## 📝 Citation & Use

If you use this framework or its concepts in academic or computational work, please cite:

> *MOGOPS‑THO Unified Framework v2.7: Civilizational Systems Analysis, Collapse Prediction, Sacred Geography, and Recovery Architecture.* TaoishTechy, May 2026. https://github.com/TaoishTechy/MOGOPS

For questions, contributions, or to propose falsification tests, please open an issue or contact the repository maintainer.

---

## 🧭 Operating Mantras

```
Do not add equations until the active ones fail.
Do not trust a pattern until it beats a null model.
Do not call a collapse until survival cases survive.
Do not let myth steer the ledger; let myth generate hypotheses.
```

> *Collapse is what the old ledger calls survival when survival no longer needs the old ledger.*

---

## 📄 License

This repository is released for academic and computational research use. All framework documents are provided as open specification materials. Specific licensing terms are set by the repository owner.

---

**MOGOPS‑THO v2.7** – *Executable Specification – Ready for Simulation, Calibration, and Falsification.*
