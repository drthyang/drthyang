# Tsung-Han Yang

**Experimental & computational materials scientist** building research tools for scattering, refinement, quantum materials, and agentic AI.

🌐 [drthyang.github.io](https://drthyang.github.io) · 💼 [LinkedIn](https://www.linkedin.com/in/thyang-profile) · ✉️ thyang.careers@gmail.com

This GitHub is a working bench: part hobby space, part research toolbox, part learning archive. I use it to try new ideas, grow scientific tools, and build toward agentic AI workflows for scattering, refinement, and materials research.

I like building at the boundary between experiments and computation: neutron/X-ray scattering, DFT, phonons, reverse Monte Carlo, browser-based visualization, AI-assisted analysis, and small software systems that make research feel less fragile.

## Featured Research Tools

The more polished pieces of the bench: zero-install scientific web apps whose analysis pipelines run client-side, so unpublished data never leaves your machine. Click a tool name to launch it in your browser.

| Tool | What it does | Highlights |
|---|---|---|
| [**MATERIA Workbench**](https://drthyang.github.io/web-refinement/) · [source](https://github.com/drthyang/web-refinement) | Refines crystal and magnetic structures — single-crystal & powder, X-ray & neutron (CW and TOF) — entirely in the browser. | AI-native by design: an MCP server exposes the same pure, tested core to LLM agents. Symmetry-constrained least squares, a magnetic space-group / k-vector workflow, validation against GSAS-II. |
| [**NEBULA3D**](https://drthyang.github.io/nebula3d/) · [source](https://github.com/drthyang/nebula3d) | Cleans 3D reciprocal-space neutron diffuse-scattering volumes and computes 3D-ΔPDF maps. | Local Pyodide pipeline with float64 analysis and large-volume support; an LLM reasoning review grades each reduction. |
| [**RMC Monitor**](https://drthyang.github.io/rmc-toolkits/) · [source](https://github.com/drthyang/rmc-toolkits) | Monitors and interprets RMCProfile fits straight from a run folder. | Live diagnostics, interactive charts, space-group detection, 3D atomic-density views, and an LLM-based AI assistant. |
| [**RMC-PH**](https://drthyang.github.io/rmc-phonon-dynamics/) · [source](https://github.com/drthyang/rmc-phonon-dynamics) | Extracts lattice dynamics from RMC ensembles fitted to experimental scattering data. | Phonon bands, DOS, animated 3D modes, and simulated INS spectra with WebGPU acceleration. |

## Agentic AI for Materials

I am building toward agentic AI for scattering and materials discovery: systems that go beyond chat and can use domain tools, understand scientific files, run refinement workflows, inspect intermediate results, and help decide what to try next.

[**MATERIA**](https://drthyang.github.io/web-refinement/) is the concrete center of that effort — an AI-native foundation for materials science, built to be driven by LLM agents as well as by people. Its scientific core is pure, side-effect-free TypeScript, so the same engine that backs the UI is exposed to agents as tools. The first agent milestone has shipped: an MCP server that lets an agent parse, build, and refine a structure, then assess the result the way an expert would — parameter correlations, at-bound values, unexplained residuals — and suggest what to try next, rather than just reporting a scalar wR.

I am still learning and prototyping in this space, but it is a direction I care about: growing MATERIA into both a useful standalone workbench and a tool/skill layer for research agents working on scattering, structure refinement, and materials analysis.

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
