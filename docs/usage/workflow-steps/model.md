---
icon: material/puzzle
---

# :material-puzzle: Model

The **Model** in EasyDiffraction represents the **crystallographic structure**
used to calculate the diffraction pattern. This pattern is then compared to
the **experimental data** to analyze and refine the structural parameters.

EasyDiffraction allows you to:

- **Load an existing model** from a **CIF file**.
- **Manually define** a new model by specifying crystallographic parameters.

Below, you will find instructions on how to define and manage crystallographic
models in EasyDiffraction. It is assumed that you have already **imported the
`easydiffraction` package** and created a **Job** object, as described in the
[Getting started](../getting-started.md) section.

## Defining a Model Manually

You can manually define a model by specifying the **space group**,
**unit cell parameters**, and **atomic positions**.

#### Example: Creating a NaCl Model

```python
# Create a phase object
phase = ed.Phase(name='nacl')

# Set space group
phase.space_group.name_hm_alt = 'F m -3 m'

# Define unit cell parameters
phase.cell.length_a = 5.691694

# Add atomic sites
phase.atom_sites.append(label='Na',
                        type_symbol='Na',
                        fract_x=0,
                        fract_y=0,
                        fract_z=0,
                        occupancy=1,
                        b_iso_or_equiv=0.5)
phase.atom_sites.append(label='Cl',
                        type_symbol='Cl',
                        fract_x=0,
                        fract_y=0,
                        fract_z=0.5,
                        occupancy=1,
                        b_iso_or_equiv=0.5)
```

## Loading a Model from a CIF File

Instead of defining the model manually, you can load a crystallographic information file (CIF) directly:

```python
# Load a phase from a CIF file
job.add_phase_from_file('data/lbco.cif')
```

## Listing Defined Phases

To check which phases have been added to the `Job`, use:

```python
print(job.phases)
```

Expected output:

```
Collection of 2 phases: ['nacl', 'lbco']
```

## Viewing a Phase as a CIF File

To inspect a phase in CIF format, use:

```python
print(job.phases['lbco'].cif)
```

Example output:

```cif
data_lbco
_cell_length_a 3.88
_cell_length_b 3.88
_cell_length_c 3.88
_cell_angle_alpha 90.00000000
_cell_angle_beta 90.00000000
_cell_angle_gamma 90.00000000
_space_group_name_H-M_ref 'P m -3 m'
_space_group_IT_coordinate_system_code 1

loop_
_atom_site_label
_atom_site_type_symbol
_atom_site_fract_x
_atom_site_fract_y
_atom_site_fract_z
_atom_site_occupancy
_atom_site_adp_type
_atom_site_B_iso_or_equiv
La La 0.00000000 0.00000000 0.00000000 0.5 Biso 0.1
Ba Ba 0.00000000 0.00000000 0.00000000 0.5 Biso 0.1
Co Co 0.5 0.5 0.5 1.00000000 Biso 0.1
O O 0.00000000 0.5 0.5 1.00000000 Biso 0.1
```

Now that the Model has been defined, you can proceed to the next step:
[Experiment](experiment.md).
