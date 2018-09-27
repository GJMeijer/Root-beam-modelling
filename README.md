# Root beam modelling

## Publication details
This code belong to publication:
    Analysis of coupled axial and lateral deformation of roots in soil
	  GJ Meijer, D Muir Wood, JA Knappett, AG Bengough, T Liang
	  International Journal for Analytical and Numerical Methods in Geomechanics
	  201x, volume x, issue x, page xx-xx
	  DOI: xxx
This code can be used to reproduce some of the shear tests with ABS described in this paper (Liang et al.)


## Quickstart
Analysis can be run by executing the <Main.py> script.
In the first lines, some user-defined settings are required
* The name of the input parameter file, including extension
* Some booleans to decide whether results should be plotted, saved etc.


## Python requirements
Code is written in Python 3
Executing required installed modules (apart from standard modules):
* SciPy
* NumPy
* MatPlotLib


# Notes on data format

## Units
Throughout the code, units used:
* Length in millimeters (mm)
* Force in newtons (N)
* Angles in radians (rad)
Note that therefore, in constrast to common geotech practice:
* Stesses and stiffnesses are in (MPa)
* Unit weights are in (N/mm3)

## Input parameter file - required parameters
Required columns:
| RunID | integer | - | Run identifier (ensure these are all unique values for every row) |
|----------------------------------------------------------|-------------|------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------|
| ModelName | string | - | Name for this analysis. Name is used to create output directory with results |
| NodeFile | string | - | File name with node input data, including .csv extension |
| SegmentFile | string | - | File name with segment input data, including .csv extension |
| phi | double | rad | Soil peak angle of internal friction (used to calculate lateral resistance) |
| phi_cs | double | rad | Soil critical state angle (used to calculate effect of soil confinement on additional shear resistance) |
| delta | double | rad | Interface friction angle between soil and root |
| gamma | double | N/mm3 | Soil effective unit weight |
| K | double | - | Coefficient of lateral earth pressure |
| sigmav0 | double | MPa | Vertical effective stress at the soil surface |
| shearplane_param | double | mm | Shear plane thickness parameter (b_sh) in paper |
| shearplane_depth | double | mm | Shear plane depth, at Y=0 |
| shearplane_angle | double | rad | Shear plane angle |
| n_node | integer | - | Number of nodes per segment |
| n_step_max | integer | - | Maximum number of displacement steps |
| n_iter_max | integer | - | maximum number of iterations (to find solution for a single displacement step) |
| uext_inc0 | double | mm | Initial shear displacement step size |
| uext_max | double | mm | Maximum shear displacement (analysis stops once this value is reached) |
| uext_factor_increase | double | - | Multiplaction factor to automatically increase displacement step size if suitable |
| uext_factor_decrease | double | - | Multiplaction factor to decrease displacement step if solution if solution not found |
| uext_incmin | double | mm | Minimum displacement step size (if lower required, analysis stops) |
| uext_incmax | double | mm | Maximum displacement step size |
| solve_tolerance | double | - | Solver tolerance of &lt;scipy.integrate.solve_bvp&gt; solver in Python |
| SaveStep | integer | - | Save full root and soil data every &lt;SaveStep&gt; displacement step |


