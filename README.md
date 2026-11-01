# Tsung-Han Yang

**Experimental & computational materials scientist** building research tools for scattering, refinement, quantum materials, and agentic AI.

🌐 [drthyang.github.io](https://drthyang.github.io) · 🎓 [Google Scholar](https://scholar.google.com/citations?user=oMIW2moAAAAJ&hl=en) · 🆔 [ORCID](https://orcid.org/0000-0003-0186-302X) · 💼 [LinkedIn](https://www.linkedin.com/in/thyang-profile) · ✉️ thyang.careers@gmail.com

This GitHub is my working bench: part research toolbox, part hobby space, part learning archive. I build at the boundary between experiments and computation (neutron/X-ray scattering, DFT, phonons, reverse Monte Carlo) and write the browser apps, AI-assisted analysis, and small software systems that make that research less fragile.

## Featured Research Tools

Zero-install scientific web apps. The analysis runs in your browser, so unpublished data stays on your machine. Click a tool name to launch it.

| Tool | Highlight |
|---|---|
| [**MATERIA Workbench**](https://drthyang.github.io/materia-platform/) · [source](https://github.com/drthyang/materia-platform)<br>Crystal and magnetic structure refinement: powder, single crystal, PDF. | Nuclear and magnetic refinement on one engine, cross-checked against GSAS-II and PDFfit2; an in-app AI Agent works the fit with you, change by change. |
| [**NeXus Viewer**](https://drthyang.github.io/neutron-nexus-viewer/) · [source](https://github.com/drthyang/neutron-nexus-viewer)<br>Slices, symmetrizes and masks 3D scattering volumes. | A first look at a 3D volume without Mantid or scripts; one click sends it to NEBULA3D. |
| [**NEBULA3D**](https://drthyang.github.io/nebula3d/) · [source](https://github.com/drthyang/nebula3d)<br>Cleans diffuse-scattering volumes into 3D-ΔPDF maps. | The full 3D-ΔPDF pipeline in the browser, up to about 80 M voxels; NEBULA Pilot, an AI agent, grades and tunes each stage. |
| [**RMCProfile Workbench**](https://drthyang.github.io/rmc-toolkits/) · [source](https://github.com/drthyang/rmc-toolkits)<br>Monitors and interprets RMCProfile fits from a run folder. | Fits, structures and atomic displacements in one place, without uploading data; AI Copilot (beta). |
| [**RMC Phonon Dynamics**](https://drthyang.github.io/rmc-phonon-dynamics/) · [source](https://github.com/drthyang/rmc-phonon-dynamics)<br>Phonons from RMC ensembles. | Turns static RMC models into lattice dynamics and simulated neutron spectra, with no computing backend. |

## Agentic AI for Scientific Software

One design across my tools: the agent calls the same tested code the buttons call, never supplies a number of its own, and each failure found on real data becomes an eval scenario.

- **[MATERIA](https://drthyang.github.io/materia-platform/)** Agent: solved the magnetic structure of a high-entropy AWO₄ from neutron powder data, end to end. It found the propagation vector, ranked the candidate magnetic space groups, and refined the moments with the nuclear model held; repeated live runs found the same k-vector, group and moment.
- **NEBULA Pilot** in [NEBULA3D](https://drthyang.github.io/nebula3d/): passed 27/27 eval runs on Claude models, 15–17/27 on local 26–32B models.
- **AI Copilot** in [RMCProfile Workbench](https://drthyang.github.io/rmc-toolkits/) (beta): checks every result in code; a computed contradiction overrides the model's verdict.
- [**NEXPLAN**](https://drthyang.github.io/nexplan/): an experiment planner (in progress) whose calculations are MCP tools that write inputs for MATERIA and NEBULA3D.
- [**Athanor**](https://github.com/drthyang/agentic-ai-materials) (exploratory): after I found and fixed two scoring defects, a fair rerun with Claude Sonnet found about 2.7× the best baseline's hits; a local 32B model did not beat the baselines.

Results and limits are on the [AI agents page](https://drthyang.github.io/agents/). This is solo work, and I am still learning in this space.

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
