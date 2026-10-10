# Sargent

**Sargent is an integrated process systems engineering platform.** One desktop application covers the whole design
loop of a chemical process: flowsheet simulation, heat integration, optimization, techno-economic and life cycle
assessment, AI prediction of reactions and properties, and links to commercial simulators and to a physical plant.

> **Version 0.0.1** is the first public build. It contains the simulator, the optimizers, the simulator links and the
> AI assistant. Heat exchanger network synthesis, TEA / LCA and the AI prediction models are not included in this
> build; their buttons are shown but disabled. They will be enabled in a later release.

## Integrated features

| Feature | What it does | 0.0.1 |
|---|---|---|
| **Flowsheet simulation** | Sequential-modular solver with automatic or user-chosen tear streams (Wegstein, Broyden, direct substitution) and compiled property kernels | Included |
| **Proxy run** | Solve the same flowsheet with Aspen Plus or DWSIM installed on your computer and bring the results and errors back; import and export Aspen Plus and DWSIM files | Included |
| **Equation-oriented optimization** | Pyomo model of the converged flowsheet, solved with IPOPT | Included |
| **Derivative-free optimization** | NSGA-II (multi-objective) or Bayesian optimization; cases run in parallel on local workers or a Ray cluster; Pareto and parallel-coordinate plots | Included |
| **Online connection** | TCP/IP connection to a reconfigurable plant (self-driving lab): module map, interlocks, wiring export. Links to PubChem, NIST Chemistry WebBook, Reaxys, SciFinder, Open Reaction Database and ASKCOS | Included (plant control in development) |
| **Agentic AI** | In-app AI assistant that reads and edits the model, runs simulations and studies (OpenAI, Anthropic or a local OpenAI-compatible server, with your own API key), and an MCP server for external AI agents | Included |
| **Heat exchanger network synthesis (HENS)** | Heat exchanger network of the solved flowsheet: matches, heat recovered, total annual cost | Not included |
| **Techno-economic analysis (TEA)** | CAPEX, OPEX, NPV and minimum selling price of the target product; tornado sensitivity | Not included |
| **Life cycle assessment (LCA)** | Cradle-to-gate and cradle-to-grave impacts per kg of product; uncertainty from the choice of LCI datasets | Not included |
| **Reaction prediction** | Forward prediction, retrosynthesis and reaction-network generation with trained graph neural networks | Not included |
| **Property prediction** | Pure-component parameters from the molecular structure: Joback (included) and graph neural networks (not included) | Joback only |

### Simulator

- Property methods: IDEAL, NRTL, WILSON, UNIQUAC, Peng-Robinson, Redlich-Kwong-Soave, Henry components, and
  electrolyte NRTL with an electrolyte wizard
- Unit operations: MIXER, FSPLIT, SEP, HEATER, HEATX, FLASH2, RADFRAC, FILTER, PUMP, COMPR, VALVE, RSTOIC, REQUIL,
  RCSTR, RPLUG and a Calculator block
- Property analysis: pure-component curves, Txy / Pxy, ternary residue-curve maps, azeotrope search, phase
  envelopes

## Installation

Python 3.12 to 3.15, Windows (64-bit). Linux builds will follow in a later release.

```
pip install "sargent[gui]"
sargent
```

Aspen Plus, DWSIM, optimization solvers (IPOPT and others) and life cycle inventory databases are not part of
Sargent. Install and license them yourself to use the features that need them.

## License

Sargent is proprietary software distributed as compiled packages only (see `LICENSE`).

- Free for academic research, teaching and personal non-commercial use.
- Commercial use requires a separate license. Contact: https://github.com/damdaepark
- Third-party components and their licenses: `THIRD_PARTY_NOTICES.md`.

## Citation

A paper describing Sargent is in preparation. Until it is published, please cite:

Damdae Park, *Sargent: an integrated process systems engineering platform*, https://github.com/damdaepark/sargent

## Name

Named in honor of Roger W. H. Sargent (1926-2018), founder of process systems engineering. Not affiliated with the
Sargent Centre for Process Systems Engineering (Imperial College London / UCL).

Copyright (c) 2026 Damdae Park. All rights reserved.
