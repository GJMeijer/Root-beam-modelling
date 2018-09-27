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

| Parameter | Type | Unit | Decription |
|-|-|-|
| RunID | Integer | - | Run identifier (ensure these are all unique values for every row)
