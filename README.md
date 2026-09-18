# Tsung-Han Yang

**Experimental & computational materials scientist** — neutron and X-ray scattering, crystallographic and magnetic symmetry, lattice dynamics, and the research software that connects a measurement to a structure.

🌐 [drthyang.github.io](https://drthyang.github.io) · 💼 [LinkedIn](https://www.linkedin.com/in/thyang-profile) · ✉️ thyang.careers@gmail.com

## Selected Publications

- **Anomalous Hall Response Induced by Correlated Disorder in the Breathing Kagome Lattice Mn₃Sn** — under review (2026) · [arXiv:2609.09699](https://arxiv.org/abs/2609.09699)
- **Intrinsic Topological Weyl Phase Transition Induced by a Magnetostructural Transformation in a Kagome Magnet** — *Nat. Commun.* **17**, 5063 (2026) · [10.1038/s41467-026-71683-7](https://doi.org/10.1038/s41467-026-71683-7)
- **Simultaneous Development of Antiferromagnetism and Local Symmetry Breaking in a Kagome Magnet (Fe₀.₅₅Co₀.₄₅)Sn** — *J. Am. Chem. Soc.* **146**, 34374 (2024) · [10.1021/jacs.4c09387](https://doi.org/10.1021/jacs.4c09387)
- **Jahn–Teller Driven Quadrupolar Ordering and Spin-orbital Dimer Formation in GaNb₄Se₈** — *Phys. Rev. B* **109**, 144101 (2024) · [10.1103/PhysRevB.109.144101](https://doi.org/10.1103/PhysRevB.109.144101)
- **Bond Ordering and Molecular Spin-orbital Fluctuations in the Cluster Mott Insulator GaTa₄Se₈** — *Phys. Rev. Research* **4**, 033123 (2022) · [10.1103/PhysRevResearch.4.033123](https://doi.org/10.1103/PhysRevResearch.4.033123)

First author on all five. [Full list](https://drthyang.github.io/publications/).

## Research Software

Tools that grew out of problems in the papers above — refining structures against measured scattering, and making the intermediate states of that process inspectable. The web apps run client-side, so unpublished data stays local. Click a name to launch it.

| Tool | What it does | Validation |
|---|---|---|
| [**MATERIA Workbench**](https://drthyang.github.io/web-refinement/) · [source](https://github.com/drthyang/web-refinement) | Refines crystal and magnetic structures in the browser — single-crystal & powder, X-ray & neutron (CW and TOF), reciprocal-space & real-space PDF — on one pure-TypeScript core. | PDF engine agrees with `diffpy.pdffit2` at correlation 0.99982 (relRMS 0.019); mPDF f(r) matches `diffpy.mpdf` to 1e-6 of peak. Symmetry-constrained least squares, magnetic space-group / k-vector workflows, symmetry-mode PDF fitting, and Bayesian posterior sampling. The same pure core is exposed to LLM agents through contract-tested MCP tools. |
| [**RMC-PH**](https://drthyang.github.io/rmc-phonon-dynamics/) · [source](https://github.com/drthyang/rmc-phonon-dynamics) | Extracts lattice dynamics from RMC ensembles fitted to experimental scattering data. | Phonon bands, DOS, animated 3D modes, and simulated INS spectra with WebGPU acceleration — bands and the S(Q,E)-derived DOS share one meV energy axis, so computed dispersion and measured spectrum read against each other. |
| [**NEBULA3D**](https://drthyang.github.io/nebula3d/) · [source](https://github.com/drthyang/nebula3d) | Cleans 3D reciprocal-space neutron diffuse-scattering volumes and computes 3D-ΔPDF maps. | Local Pyodide pipeline with float64 analysis and large-volume support. |
| [**RMCProfile Workbench**](https://drthyang.github.io/rmc-toolkits/) · [source](https://github.com/drthyang/rmc-toolkits) | Monitors and interprets RMCProfile fits straight from a run folder. | Live diagnostics, space-group detection, 3D atomic-density views, PCA thermal ellipsoids reported in the crystallographic frame, and solid-angle displacement-direction maps. |

## Applying ML to Scattering Problems

Early-stage work, and labelled as such. These repos apply pretrained models to materials questions; I have not trained or fine-tuned a model in public, and there is no held-out evaluation in them yet. That is the gap I am currently closing.

| Project | What it does | Honest status |
|---|---|---|
| [**MLIP disorder inference**](https://github.com/drthyang/mlip-disorder-inference) | Asks how much of the disorder in total-scattering data is *frozen* and how much is *motion*, using thermal ensembles from a machine-learned interatomic potential with quantum statistics as the physical null model. | Mode-projection engine reproduces published AMPLIMODES amplitudes to 0.4–3%. MACE is used as an ASE calculator, not trained. The G(r)/F(Q) forward closure is not yet quantitative. |
| [**Athanor**](https://github.com/drthyang/agentic-ai-materials) | A closed-loop LLM agent for materials discovery — states a hypothesis, proposes candidates, screens with CHGNet relaxation, convex-hull stability, and MEGNet band gaps, reflects, and iterates. Runs on local models by default. | Prototype. Compared against non-LLM baselines, though the compute budgets were not matched; the comparison is being reworked before any result is claimed. |
| [**LoRA from scratch**](https://github.com/drthyang/LoRA) | Low-rank adaptation in PyTorch with no `peft` and no `Trainer` — frozen base weights, `merge()`/`unmerge()` for zero-overhead inference, loss-masked instruction tuning. | Implementation and property tests are done; no completed training run or evaluation yet. The Conv1D transpose handling for GPT-2 was derived rather than copied. |
| [**scattering-ai-sdk**](https://github.com/drthyang/scattering-ai-sdk) | An AI reasoning layer for scattering data: detects the technique, runs deterministic diagnostics, and returns a provenance-carrying report with figures. | Deterministic analysis first, LLM interpretation second. Maximal-subgroup output validated against International Tables, including conjugate-variant counts. |

## What I Care About

Universal machine-learned interatomic potentials are evaluated almost entirely against DFT energies and forces — rarely against what an instrument actually measured. I have the scattering background and most of the pipeline to close that loop, and it is where I want to take this work next.

The other thread: crystallographic symmetry is the same mathematics as equivariance. The irreducible representations behind symmetry-mode analysis and magnetic space groups are the ones equivariant architectures are built on, and that overlap is where my background is worth the most.

## How I Tend To Build

- Start from a real research pain point, not from a technology demo
- State the null model before claiming an effect
- Make intermediate states visible, inspectable, and easier to debug
- Report a number someone else can reproduce, or don't report it
- Prefer a useful, honest prototype over a polished black box

## Stack

**Materials & scattering** — Python · NumPy/SciPy · ASE · phonopy · spglib · hiPhive · pymatgen · SMACT · h5py · symmetry-mode and magnetic space-group analysis

**ML/AI (applied)** — PyTorch · HuggingFace transformers · MACE · CHGNet · MEGNet (matgl) · MCP agent tooling

**Research software** — TypeScript/React · Vite/Vitest · WebGPU/WGSL · Pyodide · Three.js · FastAPI · pytest · GitHub Actions CI

*All projects here are personal work, developed and maintained in my personal capacity.*
