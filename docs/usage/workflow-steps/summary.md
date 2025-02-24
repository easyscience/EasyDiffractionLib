---
icon: material/clipboard-text
---

# :material-clipboard-text: Summary

The **Summary** section represents the final step in the data processing
workflow. It involves generating a **summary report** that consolidates the
results of the diffraction data analysis, providing a comprehensive overview
of the model refinement process and its outcomes.

## Contents of the Summary Report

The summary report includes key details such as:

- Final refined model parameters – Optimized crystallographic and instrumental parameters.
- Goodness-of-fit indicators – Metrics such as R-factors, chi-square (χ²), and residuals.
- Graphical representation – Visualization of experimental vs. calculated diffraction patterns.
- Background and peak analysis – Final background subtraction and peak fitting details.
- Uncertainty estimates – Error margins and confidence intervals for refined parameters.
- Data provenance – Information on input data sources, calculation engines, and refinement history.

## Exporting the Summary Report

EasyDiffraction allows exporting the summary report in various formats for
further analysis and documentation:

- Human-readable text format (.txt)
- CIF format (.cif) for integration with crystallographic databases
- PDF format (.pdf) for easy sharing and publication

## Viewing the Summary Report in EasyDiffraction

Users can view the summary directly within EasyDiffraction’s interface or
programmatically retrieve it using the Python API:

```python
# Generate and print the summary report
print(job.summary_report())
```

This command will display a structured summary of the analysis results,
including model parameters, fit statistics, and data visualizations.
