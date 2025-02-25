---
icon: material/archive
---

# :material-archive: Project

The **Project** serves as a container for all data and metadata associated with
a diffraction experiment. It acts as the top-level entity in EasyDiffraction,
ensuring structured organization and easy access to relevant information. Each
project can contain multiple **experimental datasets**, with each dataset
containing contribution from multiple **physical models**.

## Project structure

The example below illustrates a typical **project structure** for a
**constant-wavelength powder neutron diffraction** experiment:

Each file within the **Project** directory plays a crucial role in defining,
analyzing, and refining diffraction experiments.

<!-- prettier-ignore-start -->

<div class="cif">
<pre>
📁 <span class="red"><b>La0.5Ba0.5CoO3</b></span>     - Project directory.
├── 📄 <span class="orange"><b>project.cif</b></span>    - Main project description file.
├── 📁 models         - Folder with individual crystallographic phases.
│   ├── 📄 <span class="orange"><b>lbco.cif</b></span>   - File with La0.5Ba0.5CoO3 phase parameters.
│   └── ...
├── 📁 experiments    - Folder with instrumental parameters and measured data.
│   ├── 📄 <span class="orange"><b>hrpt.cif</b></span>   - Measured data from HRPT@PSI & instrumental parameters.
│   └── ...
└── 📁 summary
    └── 📄 report.cif - Summary report after structure refinement.
</pre>
</div>

<!-- prettier-ignore-end -->

## Project Files

Below is a detailed breakdown of the content within each project file.

### <span class="orange">project.cif</span>

This file provides an overview of the project, linking relevant **models** and
**experimental datasets**.

<!-- prettier-ignore-start -->

<div class="cif">
<pre>
data_<span class="red"><b>La0.5Ba0.5CoO3</b></span>

<span class="blue"><b>_project</b>.description</span> "neutrons, powder, constant wavelength, HRPT@PSI"

loop_
<span class="green"><b>_model</b>.cif_file_name</span>
lbco.cif

loop_
<span class="green"><b>_experiment</b>.cif_file_name</span>
hrpt.cif
</pre>
</div>

<!-- prettier-ignore-end -->

### models / <span class="orange">lbco.cif</span>

This file contains crystallographic information, including **space group**,
**unit cell parameters**, and **atomic positions**.

<!-- prettier-ignore-start -->

<div class="cif">
<pre>
data_<span class="red"><b>lbco</b></span>

<span class="blue"><b>_space_group</b>.name_H-M_alt</span>              "P m -3 m"
<span class="blue"><b>_space_group</b>.IT_coordinate_system_code</span> 1

<span class="blue"><b>_cell</b>.length_a</span>      3.8909(1)
<span class="blue"><b>_cell</b>.length_b</span>      3.8909
<span class="blue"><b>_cell</b>.length_c</span>      3.8909
<span class="blue"><b>_cell</b>.angle_alpha</span>  90
<span class="blue"><b>_cell</b>.angle_beta</span>   90
<span class="blue"><b>_cell</b>.angle_gamma</span>  90

loop_
<span class="green"><b>_atom_site</b>.label</span>
<span class="green"><b>_atom_site</b>.type_symbol</span>
<span class="green"><b>_atom_site</b>.fract_x</span>
<span class="green"><b>_atom_site</b>.fract_y</span>
<span class="green"><b>_atom_site</b>.fract_z</span>
<span class="green"><b>_atom_site</b>.occupancy</span>
<span class="green"><b>_atom_site</b>.adp_type</span>
<span class="green"><b>_atom_site</b>.B_iso_or_equiv</span>
La La   0   0   0     0.5  Biso 0.4958
Ba Ba   0   0   0     0.5  Biso 0.4943
Co Co   0.5 0.5 0.5   1    Biso 0.2567
O  O    0   0.5 0.5   1    Biso 1.4041
</pre>
</div>

<!-- prettier-ignore-end -->

### experiments / <span class="orange">hrpt.cif</span>

This file contains **instrumental parameters** and
**measured diffraction data**.

<!-- prettier-ignore-start -->

<div class="cif">
<pre>
data_<span class="red"><b>hrpt</b></span>

<span class="blue"><b>_diffrn_radiation</b>.probe</span>                 neutron
<span class="blue"><b>_diffrn_radiation_wavelength</b>.wavelength</span> 1.494

<span class="blue"><b>_pd_calib</b>.2theta_offset</span> 0.6225(4)

<span class="blue"><b>_pd_instr</b>.resolution_u</span>  0.0834
<span class="blue"><b>_pd_instr</b>.resolution_v</span> -0.1168
<span class="blue"><b>_pd_instr</b>.resolution_w</span>  0.123
<span class="blue"><b>_pd_instr</b>.resolution_x</span>  0
<span class="blue"><b>_pd_instr</b>.resolution_y</span>  0.0797

<span class="blue"><b>_pd_instr</b>.reflex_asymmetry_p1</span> 0
<span class="blue"><b>_pd_instr</b>.reflex_asymmetry_p2</span> 0
<span class="blue"><b>_pd_instr</b>.reflex_asymmetry_p3</span> 0
<span class="blue"><b>_pd_instr</b>.reflex_asymmetry_p4</span> 0

loop_
<span class="green"><b>_pd_phase_block</b>.id</span>
<span class="green"><b>_pd_phase_block</b>.scale</span>
lbco 9.0976(3)

loop_
<span class="green"><b>_pd_background</b>.line_segment_X</span>
<span class="green"><b>_pd_background</b>.line_segment_intensity</span>
<span class="green"><b>_pd_background</b>.X_coordinate</span>
 10  174.3  2theta
 20  159.8  2theta
 30  167.9  2theta
 50  166.1  2theta
 70  172.3  2theta
 90  171.1  2theta
110  172.4  2theta
130  182.5  2theta
150  173.0  2theta
165  171.1  2theta

loop_
<span class="green"><b>_pd_meas</b>.2theta_scan</span>
<span class="green"><b>_pd_meas</b>.intensity_total</span>
<span class="green"><b>_pd_meas</b>.intensity_total_su</span>
 10.00  167  12.6
 10.05  157  12.5
 10.10  187  13.3
 10.15  197  14.0
 10.20  164  12.5
 10.25  171  13.0
...
164.60  153  20.7
164.65  173  30.1
164.70  187  27.9
164.75  175  38.2
164.80  168  30.9
164.85  109  41.2
</pre>
</div>

<!-- prettier-ignore-end -->

Now that the Project has been defined, you can proceed to the next step:
[Model](model.md).
