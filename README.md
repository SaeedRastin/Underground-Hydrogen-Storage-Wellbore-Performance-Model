# Reproducibility package

This supplementary package accompanies the manuscript:

**A Performance-based Framework for Assessing Underground Hydrogen Storage Under Reservoir and Infrastructure Constraints: Application to Offshore Wind Curtailment Mitigation**

The files are provided to support transparency and reuse of the regional underground hydrogen storage (UHS) screening workflow. Field names have been anonymised using reservoir identifiers.

## Package contents

| File | Description |
|---|---|
| `Reservoir_inputs_Southern North Sea.csv` | Anonymised reservoir-level input table used for the regional screening workflow. It includes reservoir properties, well-status counts, and key screening attributes. |
| `Reservoir_outputs_Southern North Sea.csv` | Anonymised reservoir-level output table containing the main calculated performance metrics used in the manuscript, including wellbore-level injectivity, P50 field-scale injectivity, P50 seasonal working capacity, cushion gas, and C/W ratio. |
| `UHS_worked_example_IPR_OPR_model.ipynb` | End-to-end worked example for a single anonymised reservoir. The notebook demonstrates the analytical calculation sequence for withdrawal and injection performance, including pseudo-pressure evaluation, IPR/OPR coupling, plateau working-gas calculation, reservoir-volume-based hydrogen inventory accounting, cushion-gas accounting, and maximum theoretical wellbore-level injectivity. |


## Software requirements

The worked example was prepared in Python and requires the following packages:

```text
numpy
pandas
matplotlib
CoolProp
```

The notebook includes an automatic package check for `CoolProp`. If package installation is restricted in the execution environment, install the dependencies manually before running the notebook:

```bash
pip install numpy pandas matplotlib CoolProp
```

## How to use the worked example

1. Open `UHS_worked_example_IPR_OPR_model.ipynb` in Jupyter Notebook, JupyterLab, or a compatible Python notebook environment.
2. Run the cells sequentially.
3. The first code cell calculates withdrawal performance and seasonal storage metrics:
   - hydrogen pseudo-pressure integral,
   - laminar and non-Darcy flow coefficients,
   - IPR/OPR intersection,
   - optimum deliverability rate,
   - plateau withdrawal rate,
   - field-scale seasonal working capacity,
   - cushion gas requirement,
   - final C/W ratio.
4. The second code cell calculates injection performance:
   - injection IPR curve,
   - maximum theoretical wellbore-level hydrogen injectivity.
5. To test another reservoir, replace the input values in the **USER INPUTS** section of each cell using the corresponding parameters from `Reservoir_inputs_Southern North Sea.csv`.

## Notes on anonymisation and scope

- Reservoirs are identified using anonymised reservoir IDs.
- The package is intended to reproduce the calculation logic and key screening outputs, not to provide a full field-development model.
- The analytical model is designed for regional screening and comparison. It does not replace site-specific compositional reservoir simulation, detailed well-integrity assessment, routed offshore network design, or project-level techno-economic optimisation.
- Thermophysical properties are calculated using CoolProp. In the manuscript workflow, hydrogen compressibility and viscosity are obtained from the established hydrogen property formulations implemented in CoolProp.

## Suggested citation statement

If using this supplementary package, please cite the associated manuscript and refer to the files as the anonymised input/output dataset and worked-example notebook supporting the regional UHS screening workflow.
