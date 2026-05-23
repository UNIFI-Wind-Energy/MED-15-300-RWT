# MED-15-300-RWT
Repository for the MED 15-MW offshore reference low specific power offshore rotor. 

## Overview

The MED-15-300-RWT is a low-specific-power reference wind turbine developed for floating offshore applications in moderate-wind environments. The design targets conditions representative of the Mediterranean Sea, with the environmental basis derived from a west-of-Sicily site.


![MED-15-300-RWT](/documentation/MED-15-300-RWT.png)

## Main Charachteristics

| Parameter | Value |
| --- | --- |
| Rated power | 15 MW |
| Rotor diameter | 308 m |
| Hub height | 184 m |
| Specific power | 200 W/m^2 |
| Turbine class | IIIC |
| Rotor orientation | Upwind |
| Number of blades | 3 |
| Drivetrain | Direct drive |
| Platform concept | 4-column semi-submersible |
| Mooring concept | 3-line catenary |
| Blade mass | 94.206 t |
| RNA mass | 1237.538 t |
| Generator mass | 372.664 t |
| Tower mass | 2659.562 t |
| Semi-submersible structural mass | 5864.110 t |


## What to Cite 
Companion paper coming soon. In the meantime, please cite this repository: 

If you make use of the aerodynamic polars used in this reference turbine, please cite: 
F. Papi et al. An open database of high-fidelity, multi-Reynolds airfoil polars for wind turbine blade design, https://doi.org/10.5194/wes-11-1123-2026


## What This Repository Contains

This repository is organized around the turbine definition and the analysis models released together with it.

- `MED-15-300-RWT.yaml`: authoritative WindIO definition of the reference turbine.
- `OpenFAST/`: OpenFAST model files and related inputs for aero-servo-elastic analysis.
- `QBlade/`: QBlade model files for aerodynamic and system-level analysis.
- `LICENSE`: repository license information.


# Design Highlights
The MED-15-300-RWT was designed using the multi-disciplinary design and optimization tool QBtoWEIS (https://github.com/rbehrensdeluna/QBtoWEIS). 

### Blade Design
The MED15-300-RWT features aeroelastically-tailored blades. 

The FFA-W3 family of airfoils is used. The blade was designed accounting for variability in Reynolds number and the effect of compressibility. The airfoil coefficients are openly available - https://zenodo.org/records/17639964

The design features significant shar-twist coupling. Users are reccommended to ouse tools that are able to model the full 6x6 stiffness and mass charachteristics of the blade sections. 

Blade fine-pitch is non costant in Region #2, in order to optimize performance and limit maximum thrust. 


### Generator and Drivetrain
The MED15-300-RWT features a direct-drive permanent magnet, synchronous, radial flux generator, with an inner stator ring with a series of copper coils, and an outer rotor, which houses a series of permanent magnets. The generator was designed using GeneratorSE. For more details also see: 

Papi et al., On the prospects of derating and tailoring large offshore turbines for use in floating applications in sea basins with moderate wind speeds, proceedings of TORQUE 2026, Bruges, Belgium

### Tower 
The floating tower is a stiff-stiff design. A marfin of 20% over the nominal 3P frequency above rated wind speed is maintained. This is consistent with the maximum rotor overspeed imposed during the controller design, which is 17.5%. 
The tower is designed considering a maximum diameter of 11 meters. Nevertheless the frequency constraint is quite challenging to meet and the resulting design is quite heavy (approximately 2800 t). 
Fatigue limits were not verified at this stage.  

### Substructure and Moorings
The floater inpired by the Star-1 design developed by SAIPEM and very similar to the Volturnus-US design of the IEA-15-MW-RWT. 

key features: 
- rectangular bottom pontoons connecting the central column to the satellite ones
- co-designed to minimize tower base damage equivalent loads
- default orientation is with two upwind columns and two upwind lines. This choice was done to minimize mooring line fatigue, as shown in https://doi.org/10.5194/wes-9-1595-2024

Environmental conditions used in the design correspond to west of Sicily (Mediterranean Sea). More information can be found at https://doi.org/10.5281/zenodo.18195507 


## Performance 

Turbine performance will be documented fully in an upcoming definition document. A snapshot of the main turbine performance parameters is shown below. 

![MED-15-300-RWT](/documentation/MED_operation.png)


## Acknowledgment

This work has received the support of the FLOATFARM Project, funded by the European Union’s Horizon Europe research and innovation programme under grant agreement No. 101136091. Views and opinions expressed are however those of the author(s) only and do not necessarily reflect those of the European Union or the European Climate, Infrastructure and Environment Executive Agency (CINEA), which cannot be held responsible for them.  


## License

This repository is released under the Creative Commons Attribution 4.0 International license. See [LICENSE](LICENSE) for the full text.