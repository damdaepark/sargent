# <img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/sargent.png" alt="Sargent logo" width="48" align="top"> Sargent

[![PyPI](https://img.shields.io/pypi/v/sargent)](https://pypi.org/project/sargent/)
[![Python](https://img.shields.io/pypi/pyversions/sargent)](https://pypi.org/project/sargent/)
[![Platform](https://img.shields.io/badge/platform-Windows-blue)](https://pypi.org/project/sargent/#files)
[![License](https://img.shields.io/badge/license-proprietary%20%28free%20for%20academic%20use%29-lightgrey)](https://github.com/damdaepark/sargent/blob/main/LICENSE)

**Sargent is an integrated process systems engineering platform.** One desktop application covers the whole design
loop of a chemical process: flowsheet simulation, heat integration, optimization, techno-economic and life cycle
assessment, AI prediction of properties, and links to commercial simulators and to a physical plant.
It runs many simulations at once, on the cores of one computer or on a cluster.

> **Version 0.3** is the current public build. It contains the simulator, the optimizers, the simulator links and the
> AI assistant. Heat exchanger network synthesis, TEA / LCA and the AI prediction models are not included in this
> build; their buttons are shown but disabled. They will be enabled in a later release.

## Integrated features

| Feature | What it does | 0.3 |
|---|---|---|
| **Flowsheet simulation** | Sequential-modular solver with automatic or user-chosen tear streams (Wegstein, Broyden, direct substitution) and compiled property kernels | Included |
| **Proxy run** | Solve the same flowsheet with Aspen Plus or DWSIM installed on your computer and bring the results and errors back; import and export Aspen Plus and DWSIM files | Included |
| **Equation-oriented optimization** | Pyomo model of the converged flowsheet, solved with IPOPT | Included |
| **Derivative-free optimization** | NSGA-II (multi-objective) or Bayesian optimization; Pareto and parallel-coordinate plots | Included |
| **Parallel simulation** | Case studies and optimization cases run simultaneously in worker processes of one computer or on a Ray cluster, each with Sargent, Aspen Plus or DWSIM | Included |
| **Online connection** | TCP/IP connection to a reconfigurable plant (self-driving lab): module map, interlocks, wiring export. Links to PubChem, NIST Chemistry WebBook, Reaxys, SciFinder, Open Reaction Database and ASKCOS | Included (plant control in development) |
| **Agentic AI** | In-app AI assistant that reads and edits the model, runs simulations and studies (OpenAI, Anthropic or a local OpenAI-compatible server, with your own API key), and an MCP server for external AI agents | Included |
| **Heat exchanger network synthesis (HENS)** | Heat exchanger network of the solved flowsheet: matches, heat recovered, total annual cost | Not included |
| **Techno-economic analysis (TEA)** | CAPEX, OPEX, NPV and minimum selling price of the target product; tornado sensitivity | Not included |
| **Life cycle assessment (LCA)** | Cradle-to-gate and cradle-to-grave impacts per kg of product; uncertainty from the choice of LCI datasets | Not included |
| **Property prediction** | Pure-component parameters from the molecular structure: Joback (included) and graph neural networks (not included) | Joback only |

### Simulator

- Property methods: IDEAL, NRTL, WILSON, UNIQUAC, Peng-Robinson, Redlich-Kwong-Soave, Henry components, and
  electrolyte NRTL with an electrolyte wizard
- Unit operations: MIXER, FSPLIT, SEP, HEATER, HEATX, FLASH2, RADFRAC, FILTER, PUMP, COMPR, VALVE, RSTOIC, REQUIL,
  RCSTR, RPLUG and a Calculator block
- Property analysis: pure-component curves, Txy / Pxy, ternary residue-curve maps, azeotrope search, phase
  envelopes

### Parallel simulation

A case study (a grid or a list of input values) and the cases of an optimization are solved at the same time instead
of one after another:

- **Local**: worker processes on the cores of your computer.
- **Cluster**: the nodes of a [Ray](https://www.ray.io/) cluster (several computers);
  Sargent ships itself to the workers.

| Simulator of the cases | Local workers | Ray cluster |
|---|---|---|
| Sargent | Yes | Every node |
| Aspen Plus | Yes: one engine run per case (your license sets the number) | Windows nodes |
| DWSIM | Yes: one DWSIM instance per worker | Nodes with DWSIM installed |

Failed, unconverged or off-specification cases are flagged as infeasible; the results are shown as tables, Pareto
fronts and parallel-coordinate plots.

## Installation

Python 3.12 to 3.15 on Windows (64-bit); Linux builds follow in a later release. Package: [pypi.org/project/sargent](https://pypi.org/project/sargent/).

```
pip install "sargent[gui]"              # the desktop application
pip install "sargent[gui,parallel]"     # with Ray for cluster runs
sargent
```

Aspen Plus, DWSIM, optimization solvers (IPOPT and others) and life cycle inventory databases are not part of
Sargent. Install and license them yourself to use the features that need them. Aspen Plus runs on Windows only.

## License

Sargent is proprietary software distributed as compiled packages only (see [LICENSE](https://github.com/damdaepark/sargent/blob/main/LICENSE)).

- Free for academic research, teaching and personal non-commercial use.
- Commercial use requires a separate license. Contact: https://github.com/damdaepark
- Third-party components and their licenses: [THIRD_PARTY_NOTICES.md](https://github.com/damdaepark/sargent/blob/main/THIRD_PARTY_NOTICES.md).

## Citation

A paper describing Sargent is in preparation. Until it is published, please cite:

Damdae Park, *Sargent: an integrated process systems engineering platform*, https://github.com/damdaepark/sargent

## Name

Named in honor of Roger W. H. Sargent (1926-2018), founder of process systems engineering. Not affiliated with the
Sargent Centre for Process Systems Engineering (Imperial College London / UCL).

Copyright (c) 2026 Damdae Park. All rights reserved.
