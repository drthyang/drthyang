# Tsung-Han Yang

**Experimental & computational materials scientist** building research tools for scattering, refinement, quantum materials, and agentic AI.

🌐 [drthyang.github.io](https://drthyang.github.io) · 💼 [LinkedIn](https://www.linkedin.com/in/thyang-profile) · ✉️ thyang.careers@gmail.com

This GitHub is a working bench: part hobby space, part research toolbox, part learning archive. I use it to try new ideas, grow scientific tools, and build toward agentic AI workflows for scattering, refinement, and materials research.

I like building at the boundary between experiments and computation: neutron/X-ray scattering, DFT, phonons, reverse Monte Carlo, browser-based visualization, AI-assisted analysis, and small software systems that make research feel less fragile.

## Featured Research Tools

The more polished pieces of the bench: zero-install scientific web apps whose analysis pipelines run client-side, so unpublished data never leaves your machine. Click a tool name to launch it in your browser.

| Tool | Highlights |
|---|---|
| [**MATERIA Workbench**](https://drthyang.github.io/web-refinement/) · [source](https://github.com/drthyang/web-refinement)<br>Refines crystal and magnetic structures — single-crystal & powder, X-ray & neutron (CW and TOF), reciprocal-space & real-space PDF — entirely in the browser. | AI-native by design: an in-app Agent with 43 tools works the live fit through the page's own controls, with changes you approve and can undo, and 40 contract-tested MCP tools expose the same pure core to other LLM agents. Symmetry-constrained least squares, magnetic space-group / k-vector workflows, symmetry-mode PDF fitting, mPDF validated against `diffpy.mpdf`, and Bayesian posterior sampling — 1,800+ tests in CI, cross-checked against GSAS-II and PDFfit2. |
| [**NeXus Viewer**](https://drthyang.github.io/neutron-nexus-viewer/) · [source](https://github.com/drthyang/neutron-nexus-viewer)<br>Slices, symmetrizes and cleans 3D neutron scattering volumes (Mantid `.nxs`), ready for 3D-ΔPDF analysis. | Symmetry averaging and artifact masking you can inspect before trusting them, two-dataset comparison (e.g. two temperatures) on one split slice, and a one-click handoff of the processed volume to NEBULA3D. |
| [**NEBULA3D**](https://drthyang.github.io/nebula3d/) · [source](https://github.com/drthyang/nebula3d)<br>Cleans 3D reciprocal-space neutron diffuse-scattering volumes and computes 3D-ΔPDF maps. | Local Pyodide pipeline with float64 analysis and large-volume support; NEBULA Pilot, an AI agent on a local or cloud LLM with 22 tools, grades each stage, tunes the pipeline from a checked catalog within hard limits, and writes a measured analysis report. |
| [**RMCProfile Workbench**](https://drthyang.github.io/rmc-toolkits/) · [source](https://github.com/drthyang/rmc-toolkits)<br>Monitors and interprets RMCProfile fits straight from a run folder. | Live diagnostics, interactive charts, space-group detection, 3D atomic-density views, PCA thermal ellipsoids reported in the crystallographic frame, solid-angle displacement-direction maps, and an AI Copilot (beta) that answers questions by calling the dashboard's own analyses and checking each result. |
| [**RMC-PH**](https://drthyang.github.io/rmc-phonon-dynamics/) · [source](https://github.com/drthyang/rmc-phonon-dynamics)<br>Extracts lattice dynamics from RMC ensembles fitted to experimental scattering data. | Phonon bands, DOS, animated 3D modes, and simulated INS spectra with WebGPU acceleration — bands and the S(Q,E)-derived DOS share one meV energy axis, so computed dispersion and measured spectrum read against each other. |

## Agentic AI for Scientific Software

I add AI agents to my research tools with one design: the agent works on top of a tested scientific core, calls the same code the buttons call, and never supplies a number of its own. Rules a prompt could forget are enforced in code, failures found on real data become eval scenarios, models run locally (Ollama, LM Studio) or in the cloud, and the tools hand work to each other over MCP. Five tools follow it:

- **[MATERIA](https://drthyang.github.io/web-refinement/)**: an in-app Agent with 43 tools on the powder and PDF pages and the magnetic step. In *Ask first* mode each change waits for approval (*Auto* works through the stages), every change is an undoable History step, and the engine sets the values. It reads five agent skills on demand, follows method rules written in code (no refining parameters correlated at |ρ| ≥ 0.95, no bare occupancy, a stage checklist), and has twelve eval scenarios, each written from a real failure and replayed in CI. It writes its analysis report from the engine's numbers, and flags any number of its own that the engine didn't compute. A 40-tool MCP server opens the same core to other agents.
- **NEBULA Pilot** in [NEBULA3D](https://drthyang.github.io/nebula3d/): 22 tools over deterministic, unit-tested metrics. It grades each reduction stage, checks the ΔPDF's symmetry and coverage, tunes stage by stage from a checked catalog with a hard-limit veto, and writes a measured report (HTML/PDF or Markdown).
- **AI Copilot** in [RMCProfile Workbench](https://drthyang.github.io/rmc-toolkits/) (beta): ten of the dashboard's analyses over OpenAI-compatible tool calling, deterministic checks on each result, and an Outcome verdict. Tested with local models (gemma4, qwen3.8); its self-graded verdict still needs a human check.
- [**NEXPLAN**](https://drthyang.github.io/nexplan/) · [source](https://github.com/drthyang/nexplan): my SNS experiment planner, still in progress, as 26 MCP tools, with hand-offs that write inputs for MATERIA, NEBULA3D, and the NeXus Viewer.
- [**Athanor**](https://github.com/drthyang/agentic-ai-materials): the exploratory end. A closed-loop agent proposes compositions, screens them with physics-grounded surrogates (CHGNet relaxation, convex-hull stability, MEGNet band gaps), and is benchmarked against non-LLM baselines under the same relaxation cap (not matched total compute: the LLMs' own inference cost isn't counted). An early prototype, and reported as one.

**On real data.** MATERIA's Agent, through its fit diagnosis, found the missing peak asymmetry in GSAS-II's PbSO₄ neutron tutorial (wR 12% → 3.7%), and its Bayesian check showed that Cr₂WO₆ data cannot separate the two cations' B (P = 0.90); the cell check agrees with GSAS-II's fluorapatite cell to 1 part in 10⁵. In NEBULA3D, review rounds on a measured volume exposed a pipeline defect: six-fold partners in the ΔPDF no longer agreed, and now agree to rounding. That is a pipeline fix, not an agent result.

**Tested on real models:** my own failure-derived scenarios, run on Claude and local models (results on the [AI agents page](https://drthyang.github.io/agents/)). **Not shown yet:** two of MATERIA's five skills are first drafts. This is solo work, and I am still learning in this space.

## What You Will Find Here

- Research tools that grew out of real materials-science problems
- Browser-native apps for data analysis, visualization, and modeling
- Refinement packages and agent-ready toolsets for scattering and materials analysis
- Experiments with Pyodide, WebGPU, Three.js, scientific user experience, and agentic AI workflows
- Prototypes, notes, and learning projects from topics I am curious about

## How I Tend To Build

- Start from a real research pain point, not from a technology demo
- Keep unpublished data local whenever possible
- Make intermediate states visible, inspectable, and easier to debug
- For AI-assisted workflows, make tool calls, assumptions, and uncertainty visible
- Prefer a useful, honest prototype over a polished black box
- Use modern web technology when it makes scientific workflows easier to share

If you are interested in quantum materials, scattering, scientific visualization, agentic AI, or research software, this is where I keep the things I am actively testing and building. If you are looking for someone who can move between domain science and implementation, the projects here are meant to show both the questions I care about and how I like to solve them.

## Current Stack

Python · NumPy · SciPy · pandas · TypeScript/React · WebGPU/WGSL · Pyodide · MCP / agent tools · FastAPI/Flask · Three.js · pytest · GitHub Actions CI

For publications, research background, and CV, visit [drthyang.github.io](https://drthyang.github.io).

*All projects here are personal work, developed and maintained in my personal capacity.*
