# <img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/sargent.png" alt="Sargent logo" width="48" align="top"> Sargent

[![PyPI](https://img.shields.io/pypi/v/sargent)](https://pypi.org/project/sargent/)
[![Python](https://img.shields.io/pypi/pyversions/sargent)](https://pypi.org/project/sargent/)
[![Platform](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue)](https://pypi.org/project/sargent/#files)
[![License](https://img.shields.io/badge/license-proprietary%20%28free%20for%20academic%20use%29-lightgrey)](https://github.com/damdaepark/sargent/blob/main/LICENSE)

**Sargent is an integrated process systems engineering platform.** One desktop application covers the whole design
loop of a chemical process: flowsheet simulation, heat integration, optimization, techno-economic and life cycle
assessment, AI prediction of properties, and links to commercial simulators and to a physical plant.
It runs many simulations at once, on the cores of one computer or on a cluster.

> **Version 0.4** is the current public build. It contains the simulator, the optimizers, the simulator links and the
> AI assistant. Heat exchanger network synthesis, TEA / LCA and the AI prediction models are not included in this
> build; their buttons are shown but disabled. They will be enabled from version 1.0 on (see [Roadmap](#roadmap)).

## Feature tour

Short clips of the desktop application (sped up). Clips marked *later release* show features that are not in the
public build yet.

**AI assistant**: the assistant builds an acetone process step by step in the chat

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/02_ai_chat.gif" width="100%">

**Agentic AI**: the AI assistant builds and runs a process from a request

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/20_ai_chat_builds_process.gif" width="100%">

**Edit and undo**: every edit of the flowsheet can be undone

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/03_edit_undo.gif" width="100%">

**Import and export**: open Aspen Plus and DWSIM files, write them back

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/04_import_export.gif" width="100%">

**Built-in help (F1)**: the documentation of every block and method, with its equations

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/05_help.gif" width="100%">

**Units**: switch the unit set of the whole model instantly

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/31_flowsheeting_units.gif" width="100%">

**Components**: find components in the databanks installed on your computer

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/06_components_define.gif" width="100%">

**Electrolyte wizard**: ions, salts and reactions of an electrolyte system

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/07_elec_wizard.gif" width="100%">

**Property methods**: choose the base method of the model

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/34_property_method.gif" width="100%">

**Property parameters**: view, import and estimate the parameters (*GNN estimation: later release*)

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/10_property_parameters.gif" width="100%">

**Property analysis**: pure-component curves, Txy / Pxy, azeotropes

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/11_property_analysis.gif" width="100%">

**Search by property**: screen molecules against property criteria

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/08_screening.gif" width="100%">

**Portals**: links to public chemical databases and suppliers

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/09_portals.gif" width="100%">

**API order**: order requests to chemical suppliers through their APIs

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/19_order_api_dry_run.gif" width="100%">

**Flowsheeting**: automatic layout and name suggestions

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/13_flowsheeting.gif" width="100%">

**Intellisense**: units and streams renamed by the naming convention

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/32_intellisense.gif" width="100%">

**Reaction sets**: one Global check-box applies the chemistry to the whole model

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/27_reaction_define_global.gif" width="100%">

**Solver settings**: convergence options and the dedicated column solver

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/33_simulation_solver.gif" width="100%">

**Proxy run**: run the same model with Aspen Plus or DWSIM installed on your computer

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/14_simulation_proxy.gif" width="100%">

**Optimization setup**: variables, objectives and constraints of a problem

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/26_optimization_define.gif" width="100%">

**Equation-oriented optimization**: Pyomo model of the flowsheet solved with IPOPT

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/15_optimization_eo.gif" width="100%">

**Derivative-free optimization**: NSGA-II or Bayesian optimization on parallel workers

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/16_optimization_derivative_free.gif" width="100%">

**Live optimization monitor**: NSGA-II cases on parallel workers, the Pareto front growing

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/24_optimization_nsga2_live.gif" width="100%">

**Case table**: every study case, with the optimum design loaded back into the model

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/36_optimization_cases.gif" width="100%">

**Plant**: map blocks to plant modules and interlocks, see the plant graph

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/22_plant.gif" width="100%">

**Reaction network** (*later release*): the downhill energy diagram of a reaction network

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/12_reaction_downhill.gif" width="100%">

**Reaction network prediction** (*later release*): the network from CO2 and an amine

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/28_reaction_network.gif" width="100%">

**Byproducts** (*later release*): probability and fate of the byproducts of the main route

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/29_reaction_byproducts.gif" width="100%">

**Screening by reaction criteria** (*later release*): amines filtered by C-N bond energy, boiling point and pKa

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/30_screening_amines.gif" width="100%">

**Heat integration** (*later release*): grand composite curve and the network grid

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/17_heat_integration.gif" width="100%">

**Heat integration with MVR** (*later release*): savings of the network and the vapor recompression table

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/25_heat_integration_mvr.gif" width="100%">

**TEA** (*later release*): cost charts of the solved process

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/18_evaluation_tea.gif" width="100%">

**TEA setup** (*later release*): choose the units left out of the TEA and the heat integration

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/35_tea_configure_units.gif" width="100%">

**TEA sensitivity** (*later release*): tornado charts of the cost parameters

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/23_sensitivity_tea.gif" width="100%">

**LCA** (*later release*): climate change by raw material, utility and emission

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/21_evaluation_lca.gif" width="100%">

**LCA sensitivity** (*later release*): distribution of the impacts over the uncertain parameters

<img src="https://raw.githubusercontent.com/damdaepark/sargent/main/docs/gif/37_lca_sensitivity.gif" width="100%">

## Integrated features

| Feature | What it does | 0.4 |
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
- Unit operations: MIXER, FSPLIT, SEP, HEATER, HEATX, FLASH2, FLASH3, RADFRAC, EXTRACT, FILTER, DRYER, CRYSTALLIZER, PUMP,
  COMPR, VALVE, RSTOIC, RYIELD, REQUIL, RGIBBS, RCSTR, RPLUG, a Calculator block and design specs
- Material, heat and work streams; solids with particle size distributions
- Property parameters: estimation from the molecular structure, and regression of parameters to your own data
- Property analysis: pure-component curves, Txy / Pxy, ternary residue-curve maps, azeotrope search, phase
  envelopes

What is new in 0.4:

- Linux wheels (x86-64) next to the Windows ones.
- Property methods: UNIFAC (also for missing binary parameters), excess-Gibbs-energy mixing rules for equations of
  state, SR-POLAR, Lee-Kesler-Plocker, Braun K-10, Pitzer, and an associating equation of state for HF.
- EXTRACT block; reactors and gamma-phi methods in equation-oriented optimization; case studies.
- Search by property; order requests to chemical suppliers (MolPort, Chemspace, Mcule) with your own accounts.
- Example models. Their property parameters are not shipped: they are loaded from your own licensed Aspen Plus when
  it is installed, or you import or estimate them.
- AI assistant: one conversation per model.
- Settings scans the computer for installed simulators.

New in 0.3: FLASH3, DRYER, CRYSTALLIZER, RYIELD and RGIBBS blocks; solids; heat and work streams; design specs;
parameter regression; a monitor and a result window for equation-oriented optimization; the built-in documentation
(F1).

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

## Roadmap

- **0.x releases (now): stabilization.** The remaining 0.x releases fix bugs and make the features already included
  more robust (convergence, Aspen Plus and DWSIM import, the desktop application). Major new features are not added
  in this series.
- **1.0 and later: new features.** New features are added from version 1.0 on, starting with the ones marked
  *later release* above: heat exchanger network synthesis, TEA / LCA and the AI prediction models.

## Installation

Python 3.12 to 3.15 on Windows (64-bit) and Linux (x86-64, glibc 2.17 or newer). Package: [pypi.org/project/sargent](https://pypi.org/project/sargent/).

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
