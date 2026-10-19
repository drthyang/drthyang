# Tsung-Han Yang

**Experimental & computational materials scientist** building research tools for scattering, refinement, quantum materials, and agentic AI.

🌐 [drthyang.github.io](https://drthyang.github.io) · 💼 [LinkedIn](https://www.linkedin.com/in/thyang-profile) · ✉️ thyang.careers@gmail.com

This GitHub is my working bench: part research toolbox, part hobby space, part learning archive. I build at the boundary between experiments and computation (neutron/X-ray scattering, DFT, phonons, reverse Monte Carlo) and write the browser apps, AI-assisted analysis, and small software systems that make that research less fragile.

## Featured Research Tools

Zero-install scientific web apps. Their analysis pipelines run client-side, so unpublished data never leaves your machine. Click a tool name to launch it in your browser.

| Tool | Highlights |
|---|---|
| [**MATERIA Workbench**](https://drthyang.github.io/materia-platform/) · [source](https://github.com/drthyang/materia-platform)<br>Refines crystal and magnetic structures — single-crystal & powder, X-ray & neutron (CW and TOF), reciprocal-space & real-space PDF — entirely in the browser. | Symmetry-constrained least squares, magnetic space-group / k-vector workflows, symmetry-mode PDF fitting, mPDF validated against `diffpy.mpdf`, and Bayesian posterior sampling — 1,800+ tests in CI, cross-checked against GSAS-II and PDFfit2. AI-native by design: an in-app Agent and an MCP server work the same core ([below](#agentic-ai-for-scientific-software)). |
| [**NeXus Viewer**](https://drthyang.github.io/neutron-nexus-viewer/) · [source](https://github.com/drthyang/neutron-nexus-viewer)<br>Slices, symmetrizes and cleans 3D neutron scattering volumes (Mantid `.nxs`), ready for 3D-ΔPDF analysis. | Symmetry averaging and artifact masking you can inspect before trusting them, two-dataset comparison (e.g. two temperatures) on one split slice, and a one-click handoff of the processed volume to NEBULA3D. |
| [**NEBULA3D**](https://drthyang.github.io/nebula3d/) · [source](https://github.com/drthyang/nebula3d)<br>Cleans 3D reciprocal-space neutron diffuse-scattering volumes and computes 3D-ΔPDF maps. | Local Pyodide pipeline with float64 analysis and large-volume support, plus NEBULA Pilot, an AI agent that grades and tunes each stage ([below](#agentic-ai-for-scientific-software)). |
| [**RMCProfile Workbench**](https://drthyang.github.io/rmc-toolkits/) · [source](https://github.com/drthyang/rmc-toolkits)<br>Monitors and interprets RMCProfile fits straight from a run folder. | Live diagnostics, interactive charts, space-group detection, 3D atomic-density views, PCA thermal ellipsoids reported in the crystallographic frame, solid-angle displacement-direction maps, and an AI Copilot (beta). |
| [**RMC-PH**](https://drthyang.github.io/rmc-phonon-dynamics/) · [source](https://github.com/drthyang/rmc-phonon-dynamics)<br>Extracts lattice dynamics from RMC ensembles fitted to experimental scattering data. | Phonon bands, DOS, animated 3D modes, and simulated INS spectra with WebGPU acceleration — bands and the S(Q,E)-derived DOS share one meV energy axis, so computed dispersion and measured spectrum read against each other. |

## Agentic AI for Scientific Software

My research tools share one agent design: the agent works on top of a tested scientific core, calls the same code the buttons call, and never supplies a number of its own. Rules a prompt could forget are enforced in code, failures found on real data become eval scenarios, models run locally (Ollama, LM Studio) or in the cloud, and the tools hand work to each other over MCP. Five tools follow it:

- **[MATERIA](https://drthyang.github.io/materia-platform/)**: an in-app Agent with 43 tools on the powder and PDF pages and the magnetic step, and a 40-tool, contract-tested MCP server that opens the same core to other agents.
  - In *Ask first* mode each change waits for approval (*Auto* works through the stages). Every change is an undoable History step, and the engine sets the values.
  - It reads five agent skills on demand and follows method rules written in code: no refining parameters correlated at |ρ| ≥ 0.95, no bare occupancy, a stage checklist.
  - Twelve eval scenarios, each written from a real failure, replay in CI. Its analysis report uses the engine's numbers and flags any number the engine didn't compute.
- **NEBULA Pilot** in [NEBULA3D](https://drthyang.github.io/nebula3d/): 22 tools over deterministic, unit-tested metrics, on a local or cloud LLM. It grades each reduction stage, checks the ΔPDF's symmetry and coverage, tunes stage by stage from a checked catalog with a hard-limit veto, and writes a measured report (HTML/PDF or Markdown).
- **AI Copilot** in [RMCProfile Workbench](https://drthyang.github.io/rmc-toolkits/) (beta): ten of the dashboard's analyses over OpenAI-compatible tool calling, deterministic checks on each result, and an Outcome verdict. Tested with local models (gemma4, qwen3.8); its self-graded verdict still needs a human check.
- [**NEXPLAN**](https://drthyang.github.io/nexplan/) · [source](https://github.com/drthyang/nexplan): my SNS experiment planner, still in progress, as 26 MCP tools, with hand-offs that write inputs for MATERIA, NEBULA3D, and the NeXus Viewer.
- [**Athanor**](https://github.com/drthyang/agentic-ai-materials): the exploratory end. A closed-loop agent proposes compositions, screens them with physics-grounded surrogates (CHGNet relaxation, convex-hull stability, MEGNet band gaps), and is benchmarked against non-LLM baselines under the same relaxation cap (not matched total compute: the LLMs' own inference cost isn't counted). An early prototype, and reported as one.

**On real data.** MATERIA's Agent, through its fit diagnosis, found the missing peak asymmetry in GSAS-II's PbSO₄ neutron tutorial (wR 12% → 3.7%), and its Bayesian check showed that Cr₂WO₆ data cannot separate the two cations' B (P = 0.90); the cell check agrees with GSAS-II's fluorapatite cell to 1 part in 10⁵. In NEBULA3D, review rounds on a measured volume exposed a pipeline defect: six-fold partners in the ΔPDF no longer agreed, and now agree to rounding. That is a pipeline fix, not an agent result.

**Tested on real models:** my own failure-derived scenarios, run on Claude and local models (results on the [AI agents page](https://drthyang.github.io/agents/)). **Not shown yet:** two of MATERIA's five skills are first drafts. This is solo work, and I am still learning in this space.

## How I Build

- Start from a real research pain point, not from a technology demo.
- Keep unpublished data local whenever possible.
- Make intermediate states, and for AI workflows the tool calls, assumptions, and uncertainty, visible and inspectable.
- Prefer a useful, honest prototype over a polished black box.
- Use modern web technology (Pyodide, WebGPU, Three.js) when it makes scientific workflows easier to share.

Besides the tools above, you will find refinement packages, prototypes, notes, and learning projects on topics I am curious about. If you are looking for someone who moves between domain science and implementation, these projects show both the questions I care about and how I like to solve them.

## Current Stack

Python · NumPy · SciPy · pandas · TypeScript/React · WebGPU/WGSL · Pyodide · MCP / agent tools · FastAPI/Flask · Three.js · pytest · GitHub Actions CI

For publications, research background, and CV, visit [drthyang.github.io](https://drthyang.github.io).

*All projects here are personal work, developed and maintained in my personal capacity.*
