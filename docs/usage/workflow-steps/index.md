# Workflow steps

To streamline the **data analysis process**, EasyDiffraction follows a
structured workflow divided into **five key steps**:

```mermaid
flowchart LR
    a(Project)
    b(Model)
    c(Experiment)
    d(Analysis)
    e(Summary)
    a --> b
    b --> c
    c --> d
    d --> e
```

- [:material-archive: Project](project.md) - Establish a **project** as a
  container for data, settings, and analysis results.
- [:material-puzzle: Model](model.md) - Load an existing
  **crystallographic model** in CIF format or define a new one from scratch.
- [:material-microscope: Experiment](experiment.md) - Import
  **experimental diffraction data** and configure **instrumental parameters**.
- [:material-calculator: Analysis](analysis.md) - Calculate the
  **diffraction pattern** and optimize the structural model by refining
  parameters to match experimental measurements.
- [:material-clipboard-text: Summary](summary.md) - Generate a
  **detailed report** summarizing the results of the analysis, including
  refined parameters and visualizations.

Each step is described in detail in its respective section, guiding users
through the **entire diffraction data analysis workflow** in
EasyDiffraction.
