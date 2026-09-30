# Carbon capture in steam methane reforming – process simulation and LCA

Gate-to-gate life cycle assessment of CO₂ capture and compression in a steam methane reforming (SMR) hydrogen plant. Team project (4 students, "Team Gen Alpha") for the course Sustainability Assessment (LCA), Faculty of Process and Systems Engineering, Otto von Guericke University Magdeburg, summer semester 2026. Supervisor: Prof. Dr. Liisa Rihko-Struckmann.

Report: `LCA Sprint 3 Final .pdf` · LaTeX source: `LCA_Sprint3_Final.tex` · [Overleaf (read-only)](https://www.overleaf.com/read/dgffffrgnmvg#042823)

## What we modelled

SMR is the main industrial route to hydrogen and a large CO₂ source. We asked what material and energy it takes to capture and compress 1 kg of CO₂ from an SMR plant.

The DWSIM flowsheet (Peng-Robinson equation of state) has three sections:

1. **Reformer:** CH₄ + H₂O ⇌ CO + 3H₂
2. **Water-gas shift reactor:** CO + H₂O ⇌ CO₂ + H₂
3. **CO₂ separation and compression:** PSA unit for hydrogen, gas-liquid and compound separators for the CO₂-rich off-gas, then three compressor stages with intercooling to 110 bar (supercritical)

Feed: 10 kg/h methane, 30 kg/h steam. Products: 2.11 kg/h hydrogen at 200 bar, 10.2 kg/h CO₂-rich stream (94.7 mol % CO₂) at 110 bar.

The inventory was then modelled in OpenLCA following ISO 14040/14044, with a functional unit of **1 kg of captured CO₂**.

## Results

| Metric | Value |
|---|---|
| CO₂ recovery from the PSA off-gas | 88 % (10.0 of 11.4 kg/h CO₂) |
| Methane per kg CO₂ captured | 0.979 kg |
| Steam per kg CO₂ captured | 2.94 kg |
| Compressor power, stages 1 / 2 / 3 | 0.19 / 0.16 / 0.04 kW (0.39 kW total) |
| Compression energy per kg CO₂, stages 1 / 2 / 3 | 0.067 / 0.057 / 0.015 MJ (≈ 0.14 MJ total) |
| Intercooler heat removed | 1.13 kW (0.40 MJ/kg CO₂) |
| Largest steel use | Cooler 8, 1.5 × 10⁻⁴ kg per kg CO₂ |

- Most compression work is done in the first two stages; the last stage adds the least.
- The intercoolers remove about three times as much heat as the compressors use in electricity, so cooling is the largest energy flow in the capture section.
- The 12 % of CO₂ that isn't recovered leaves with the fuel gas to the reformer furnace, so it is emitted, not captured.

## System boundary

Gate-to-gate: from natural gas inlet to compressed CO₂ ready for transport.

- **Included:** methane and steam inputs, CO₂ separation and compression, steel in the capture equipment, compressor electricity
- **Excluded:** natural gas extraction and pipeline transport, plant construction and decommissioning, CO₂ transport and storage, use of the hydrogen

Air Liquide's CRYOCAP™ H₂ unit at Port-Jérôme (France) served as the industrial reference for capturing CO₂ from SMR off-gas; it uses cryogenic separation, which we did not model.

## Tools

| Tool | Used for |
|---|---|
| DWSIM | Process simulation (Peng-Robinson) |
| OpenLCA | Life cycle inventory and impact assessment |
| ISO 14040/14044 | LCA method |
| LaTeX / Overleaf | Report |

## Key references

- Spath, P. L. & Mann, M. K. (2001). *Life Cycle Assessment of Hydrogen Production via Natural Gas Steam Reforming.* NREL.
- Dufour, J. et al. (2009). Life cycle assessment of hydrogen production by steam reforming. *Int. J. Hydrogen Energy*, 34(3), 1370–1376.
- IEAGHG (2017). *Techno-economic evaluation of SMR-based hydrogen plant with CCS.* Report 2017/02.
- Antonini, C. et al. (2020). Hydrogen production from natural gas and biomethane with carbon capture and storage – a techno-environmental analysis. *Sustainable Energy & Fuels*, 4(6), 2967–2986.
- ISO 14040:2006. *Environmental management – Life cycle assessment – Principles and framework.*

Full list in the report.
