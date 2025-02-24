---
icon: material/calculator
---

# :material-calculator: Analysis

This section provides an overview of **diffraction data analysis** in
EasyDiffraction, focusing on model-dependent analysis, calculation engines,
and minimization techniques.

### Model-dependent analysis

There are two general approaches to the analysis:

- **Model-Independent Analysis** – No assumptions are made about the system;
  conclusions are drawn purely from observed data.
- **Model-Dependent Analysis** – A mathematical model is developed to describe
  the system, incorporating known physical and chemical principles.

In EasyDiffraction, we focus on **model-dependent analysis**, where a model is
constructed based on prior knowledge of the system, and its parameters are
optimized to achieve the best agreement between experimental and calculated
diffraction data.

#### Workflow of model-dependent analysis

The process of refining a model involves iterating through multiple steps until
the calculated data sufficiently matches the experimental data. This
process is illustrated below:

```mermaid
flowchart LR
    a(Propose<br/>model)
    b(Set/change<br/>model<br/>parameter<br/>values)
    c(Calculate<br/>model<br/>data)
    d(Compare<br/>model data to<br/>experimental<br/>data)
    e(Stop<br/>iteration)
    a --> b
    b --> c
    c --> d
    d-- Threshold<br/>not<br/>reached -->b
    d-- Threshold<br/>reached -->e
```

Model-dependent analysis is popular in the analysis of neutron scattering data,
and we will use it in the following examples.

Model-dependent analysis is widely used in **neutron and X-ray diffraction
studies**, where refining model parameters enables a deeper understanding of
material structures.

## Calculation engines

EasyDiffraction is designed as a flexible and extensible tool that supports
different **calculation engines** for diffraction pattern simulations.
Currently, we integrate:

### [CrysPy](https://www.cryspy.fr)

CrysPy is a Python library originally developed for analysing polarised neutron
diffraction data. It is now evolving into a more general purpose library and
covers powders and single crystals, nuclear and (commensurate) magnetic
structures, unpolarised neutron and X-ray diffraction.

### [CrysFML](https://code.ill.fr/scientific-software/CrysFML2008)

This library is a collection of Fortran modules for crystallographic computations.
It is used in the software package [FullProf](https://www.ill.eu/sites/fullprof/), and we are
currently working on its integration into EasyDiffraction.

## Minimisation engines

EasyDiffraction utilizes various third-party libraries for model refinement
and parameter optimization. These libraries provide robust curve fitting and
uncertainty estimation tools.

Most of the examples in this section will use the
[lmfit](https://lmfit.github.io/lmfit-py/) package, which provides a high-level
interface to non-linear optimisation and curve fitting problems for Python. It
is one of the tools that can be used to fit models to the experimental data.

Another package that can be used for the same purpose is
[bumps](https://bumps.readthedocs.io/en/latest/). In addition to traditional
optimizers which search for the best minimum they can find in the search space,
bumps provides Bayesian uncertainty analysis which explores all viable minima
and finds confidence intervals on the parameters based on uncertainty in the
measured values.
