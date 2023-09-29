# Explicit-Formulas Database
A fork of [J08nY](https://github.com/J08nY)'s [export](https://github.com/crocs-muni/efd) of the [Explicit-Formulas Database](https://www.hyperelliptic.org/EFD/) (EFD).


## Differences to crocs-muni/efd

Homogeneity weights has been added to each coordinate system. This is a file that contains weight (integer) for each variable in the coordinate system. Each formula (meaning the rational functions) are then (quasi)-homogenous with respect to these weights.

For each coordiante system there is a file `unified_transformation` defining transformation to a simple affine form. Some formulas have specific transformation file that overrule the transformations defined for the coordinate system. Each file contains a series of the following steps:
  - remove_yz2 : (Edwards form) Substitute Y =r*Y^2 and subtitute d=r^2, c=1
  - remove_yz : (Edwards form) Substitute Y =r*Y and subtitute d=r^2, c=1
  - xproject : (xmadd-2007-hcd) Substitute  Z1=1 and Z2=1/x2, Y2=y2/x2
  - Z_to_1 : Substitute Z = 1 (including ZZ)
  - xinvert : (xmadd-2007-bl) Substitute Z1=1 and Z2=x2, Y2=x2/y2, Y1=1/y1,X1=1/x1
  - T_to_xy : Substitute T = X*Y
  - invert : Substitute X = 1/X, Y = 1/Y
  - T_to_a : Substitute T = a
