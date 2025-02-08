# MultimerPaper2024
Input Files for the 2024 Alzheimer's &amp; Dementia Manuscript Entitled "Multimerization of TREM2 is impaired by Alzheimer's disease-associated variants"

Each subdirectory contains the necessary input files used for the simulation of a single variant complex model. Subdirectories are named according to the variant name within the manuscript.

UAB High Performance Computing's Cheaha cluster only allows individual runs up to 150 hours, so simulations are split into multiple segments and main text MD simulations are run in triplicate.
The order of these segments from the end of the heating protocol (at 300K) for each variant is as follows:

eq-300K.rst --md.in--> md.rst --ext.in--> ext.rst --ext.in--> ext2.rst --ext.in--> ext3...

Types of input files:

.rst -> "restart" coordinate files for the starting frame of each segment of the trajectory.

SolvI.prmtop -> parameter/topology files describing the atoms (protein, solvent, ions) associated with the simulations. Each variant was run with a single SolvI.prmtop file throughout.

.in & .job -> input parameters and command files to begin a run from a set of coordinates and a parameter/topology using AMBER. As stated above, md.in was used for the initial step of the simultaion and ext.in was used to extend the MD simulations for all following steps.

Final trajectories in binary .binpos format are available from the Open Science Framework at (main: https://osf.io/km429/ and supplemental: https://osf.io/8hqkj/). As these .binpos files have solvent and ions stripped for efficient storage, they should be used with the md.prmtop files (i.e., rather than with the SolvI.prmtop files used as simulation inputs). Other trajectory formats (including human readable or containing solvent/ions/unit cell information) are available upon request.

All simulations were carried out using the AMBER suite (ambermd.org) and AMBER ff14sb force fields. Additional information, including hardware specifications, is contained within the manuscript text. DOI: https://doi.org/10.1002/alz.14124
