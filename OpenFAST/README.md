# MED-15-300-RWT

Repository for the OpenFAST model of the MED 15 MW offshore reference wind turbine developed within the FLOATFARM project. Model files target OpenFAST v5.

notes: 
1. The bottom pontoons are modeled as rectangular members in HydroDyn, matching the actual floater geometry (this requires OpenFAST v5, since earlier OpenFAST versions only support cylindrical members).
2. ElastoDyn does not support tower torsion. The yaw bearing DOF is therefore enabled, with an equivalent yaw stiffness, as an approximation for tower torsional flexibility.
3. Blade structural damping is higher than in the equivalent QBlade model, to address numerical instabilities observed in DLC simulations. Current values (percent of critical damping): flapwise/edgewise 1.0% (QBlade: 0.35%), torsion 2.0% (QBlade: 0.5%).


