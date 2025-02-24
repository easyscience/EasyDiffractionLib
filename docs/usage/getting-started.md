# Getting started

## Importing EasyDiffraction

To start using EasyDiffraction, first import the package in your Python
script or Jupyter Notebook:
```python
import easydiffraction as ed
```

## Creating a job object

The **Job** object is central to EasyDiffraction, storing all necessary
information for performing diffraction calculations. Below is an example of how
to create a Job object:
```python
job = ed.Job()
```

This object serves as a container for **model definitions**,
**experimental data**, and **analysis settings**.

## Data analysis workflow

Once the Job object is created, you can proceed with the
**data analysis workflow**, which is described in detail in the
[Workflow steps](workflow-steps/index.md) section of the documentation.
