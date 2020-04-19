### Readme

This repository contains force field parameters for simulating
9-O-acetyl, 9-N-acetyl and 9-hydroxyl sialic acid residues, with
torsion parameters fitted to wB97X-D3/6-31++g(2d,2p) level of theory
using the TorsionDrive/ForceBalance software packages.  It also
includes parameters for a propyl azide residue as part of the
simulated GM3 glycans.

These files accompany the manuscript "A combined NMR, MD and DFT
conformational analysis of 9-O-acetyl sialic acid-containing GM3
ganglioside glycan and its 9-N-acetyl mimic" submitted to Glycobiology,
currently in revision.

### Files

`amber/` : Sialic acid residue template and parameter files for AMBER.

`azide-params/` : Residue template and parameter files for propyl azide residue.

`example/` : Example folders showing how to set up the systems in the publication.

`reference/` : Original simulation input files for the publication.

### Installation

After sourcing your AMBER environment variables, the sialic acid
residue templates and parameter files should be installed in the
following way:

rsync -av amber/dat/ $AMBERHOME/dat/

Note that sourcing these parameter files will override the existing
GLYCAM parameters for "9-hydroxyl" sialic acid. This was done because
we wanted to compare the three forms of sialic acid on equal footing.

To use the original GLYCAM parameters for "9-hydroxyl" sialic acid,
simply do not source the leaprc.GLYCAM_06j_9acsia file.

### Usage

The systems containing the custom sialic acids were built using the
sequence command in tleap after loading the residue templates and
parameter files.  Example tleap input files files are given in the
example/ subfolders, such as example/NAc-setup/setup.leap.

After installation and making sure that AZI.prep and AZI.frcmod are
contained in the folder, simply run:

```tleap -f setup.leap```

The parm7 / rst7 (i.e. prmtop / inpcrd) files produced by running this
command are provided in the repo.  The simulation input files used
for the publication are provided for comparison.  The files are identical
except for some tiny differences in the last decimal place of some angle
force constants in 9-NAc which should be inconsequential (less than 0.01%).

### Citation

If these files have benefited your research, please support us by citing:
(reference will be added after publication)
