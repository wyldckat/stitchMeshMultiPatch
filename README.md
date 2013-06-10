stitchMeshMultiPatch
====================

This utility was derived from OpenFOAM® 2.2.x (commit ff9ffb9699bd9c66baeb9d4460606102180f711b) own `stitchMesh` utility, which can be found in the `vanilla` branch of the current repository.

The objective was to give the ability to stitch more than one patch pair in a single run. This was achieved by using a single dictionary where we can define the pairs to stitch together and with which stitching criteria.

It has been created as an attempt for this thread: http://www.cfd-online.com/Forums/openfoam-meshing-utilities/113863-when-can-stitchmesh-used.html

Disclaimer and License
======================

This offering is not approved or endorsed by OpenCFD Limited, the producer of the OpenFOAM software and owner of the OPENFOAM® and OpenCFD® trade marks.

This is bound to the same license as OpenFOAM, namely GNU Public License v3. Quoting from OpenFOAM's license statement:

    OpenFOAM is free software: you can redistribute it and/or modify it
    under the terms of the GNU General Public License as published by
    the Free Software Foundation, either version 3 of the License, or
    (at your option) any later version.

    OpenFOAM is distributed in the hope that it will be useful, but WITHOUT
    ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or
    FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License
    for more details.

    You should have received a copy of the GNU General Public License
    along with OpenFOAM. If not, see <http://www.gnu.org/licenses/>.



How to get+build stitchMeshMultiPatch
======================================

These instructions are for OpenFOAM 2.2.x:

For getting and building from git:
```
git clone git://github.com/wyldckat/stitchMeshMultiPatch.git
cd stitchMeshMultiPatch
git checkout master
wmake
```

For getting and building from zip:
```
wget "https://github.com/wyldckat/stitchMeshMultiPatch/archive/master.zip" -O stitchMeshMultiPatch.zip
cd stitchMeshMultiPatch-master
wmake
```

How to use it
=============

Intead of using, e.g.:
```
stitchMesh -partial -toleranceDict toleranceDict -overwrite sideA sideB
stitchMesh -partial -toleranceDict toleranceDict -overwrite sideC sideD
```

We can use instead:
```
stitchMeshMultiPatch -toleranceDict toleranceDict -overwrite
```

Along with the file `stitchMeshMultiPatchDict`, that should already be placed in the case's `system` folder.
The example file is accessible here: https://github.com/wyldckat/stitchMeshMultiPatch/blob/master/stitchMeshMultiPatchDict


Authorship
==========

This `stitchMeshMultiPatch` utility was created by Bruno Santos (wyldckat@github).

Code is completely based on the original `stitchMesh` from OpenFOAM 2.2.x, as well as `createPatch` for the dictionary part.

So in essence, it was a lot of _precision copy-paste-adapt_ coding.
