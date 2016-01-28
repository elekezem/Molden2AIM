<img src="https://raw.githubusercontent.com/zorkzou/Molden2AIM/master/m2a-logo.png" />

# Molden2AIM
Molden2AIM is a utility program which can be used to creat AIM-WFN and NBO-47 files from a Molden file.

## Recent Changes
Version 3.3.0 (01/24/2016).

1. Calculates the generalized Wiberg bond order indices (GWBO) in MO.

Version 3.2.0 (12/18/2015).

1. Supports the MOLDEN files generated by [NBO6 (> May.2014)](http://nbo6.chem.wisc.edu/).
2. Supports MOLDEN files generated by the [Molden](http://www.cmbi.ru.nl/molden/) program. [Molden](http://www.cmbi.ru.nl/molden/) can read geometry, basis functions, and MOs from the output file of [Gaussian](http://www.gaussian.com/)/[Gamess](http://www.msg.chem.iastate.edu/gamess/)/[Gamess-UK](http://www.cfs.dl.ac.uk/)/[Firefly](http://classic.chem.msu.su/gran/gamess/)/[Q-Chem](http://www.q-chem.com/).
3. The GAB file generated by [Gabedit](http://gabedit.sourceforge.net/) is compatible. Gabedit can read geometry, basis functions, and MOs from the output file of [Gaussian](http://www.gaussian.com/)/[Gamess](http://www.msg.chem.iastate.edu/gamess/)/[Firefly](http://classic.chem.msu.su/gran/gamess/).

Version 3.1.0 (02/25/2015).

1. Supports the MOLDEN files generated by [NWChem](http://www.nwchem-sw.org/), [BDF](http://www.chem.pku.edu.cn/page/ITCC/research/lwj/BDF.htm) (GTO only), [PSI4](http://www.psicode.org/) (spherical functions only), [CADPAC](http://www-theor.ch.cam.ac.uk/software/cadpac.html), and [MRCC](http://www.mrcc.hu/).
2. Bug fix for [NBO6](http://nbo6.chem.wisc.edu/).
3. ReOrdAtm.f90 has been updated for [CFour](http://www.cfour.de/).
4. Check the normalization of [NBO](http://nbo6.chem.wisc.edu/)'s *.47 file.

## Features

* It converts the data format from Molden to AIM's WFN. The latter format can be read by [AIMPAC](http://www.chemistry.mcmaster.ca/aimpac/imagemap/imagemap.htm), [AIMPAC2](http://www.beaconresearch.org/AIMPAC2/index.html), [AIM2000](http://www.aim2000.de/), [AIMALL](http://aim.tkgristmill.com/), [AIM-UC](http://alfa.facyt.uc.edu.ve/quimicomp/), [DensToolKit](https://sites.google.com/site/jmsolanoalt/software/denstoolkit), [DGrid](http://www.cpfs.mpg.de/~kohout/dgrid.html), [MORPHY98](http://morphy.mib.man.ac.uk/), [Multiwfn](http://multiwfn.codeplex.com/), [PAMoC](http://www.istm.cnr.it/~barz/pamoc/), [ProMolden](http://azufre.quimica.uniovi.es/d-DensEl/), [TopChem](http://www.lct.jussieu.fr/pagesperso/pilme/topchempage.html), [TopMoD](http://www.lct.jussieu.fr/pagesperso/silvi/topmod.html), [Xaim](http://www.quimica.urv.es/XAIM/), and so on. The GAB file of [Gabedit](http://gabedit.sourceforge.net/) is compatible.
* It saves [NBO](http://nbo6.chem.wisc.edu/)'s *.47 data file. One can do NBO analysis using the stand-alone [GENNBO](http://nbo6.chem.wisc.edu/) program. In addition, the following loops can be performed using [NBO](http://nbo6.chem.wisc.edu/). However the results may be different since [NBO6](http://nbo6.chem.wisc.edu/) saves natural bond orbitals (NBOs) by default.

<img src="https://raw.githubusercontent.com/zorkzou/Molden2AIM/master/m2a-loop.png" />

* After the *.47 file being generated, it can calculate the generalized Wiberg bond order indices (GWBO) in MO (see I. Mayer, C.P.L. 97, 270, 1983). In the case of closed-shell system, they are the Mayer bond orders (MBO) in MO.

The WFX format will be supported in the future.

## Compilation

    > F90 -O3 molden2aim.f -o molden2aim.exe

here `F90` can be `gfortran`, `g95`, `pgf90`, `ifort`, or other FORTRAN90 compilers.

## Running Molden2AIM

-   Windows

1. Put `molden2aim.exe`, MOLDEN file, and (optional) `m2a-dos.ini` into the same folder.
2. Rename `m2a-dos.ini` to `m2a.ini`.
3. If necessary, insert a [Program] line into the MOLDEN file, or edit the program parameter in `m2a.ini` (you can also setup other parameters there).
4. Double-click `molden2aim.exe`, and then type in the name of the MOLDEN file.

-   Unix/Linux/MacOS

1. Put `molden2aim.exe`, MOLDEN file, and (optional) `m2a-unix.ini` into the same folder.
2. Rename `m2a-unix.ini` to `m2a.ini`.
3. If necessary, insert a [Program] line into the MOLDEN file, or edit the program parameter in `m2a.ini` (you can also setup other parameters there).
4. In the terminal, type in

    > ./molden2aim.exe

   and then type in the name of the MOLDEN file.

## About the Molden file

MOLDEN (or GAB) files generated by the the following programs are fully or partly supported by Molden2AIM at present.

* [ACES-II](http://www.qtp.ufl.edu/ACES/) (> 2.9)
* [BDF](http://www.chem.pku.edu.cn/page/ITCC/research/lwj/BDF.htm) (GTO only)
* [CADPAC](http://www-theor.ch.cam.ac.uk/software/cadpac.html)
* [CFour](http://www.cfour.de/)
* [Columbus](http://www.univie.ac.at/columbus/)
* [DALTON](http://daltonprogram.org/) (> 2013)
* [deMon2k](http://www.demon-software.com/public_html/)
* [Firefly](http://classic.chem.msu.su/gran/gamess/), through the utilities [Molden](http://www.cmbi.ru.nl/molden/) or [Gabedit](http://gabedit.sourceforge.net/). See [molden_gabedit.jpg](https://raw.githubusercontent.com/zorkzou/Molden2AIM/master/molden_gabedit.jpg).
* [Gaussian](http://www.gaussian.com/), through the utilities [Molden](http://www.cmbi.ru.nl/molden/) or [Gabedit](http://gabedit.sourceforge.net/). See [molden_gabedit.jpg](https://raw.githubusercontent.com/zorkzou/Molden2AIM/master/molden_gabedit.jpg).
* [Gamess](http://www.msg.chem.iastate.edu/gamess/), through the utilities [Molden](http://www.cmbi.ru.nl/molden/) or [Gabedit](http://gabedit.sourceforge.net/). See [molden_gabedit.jpg](https://raw.githubusercontent.com/zorkzou/Molden2AIM/master/molden_gabedit.jpg).
* [Gamess-UK](http://www.cfs.dl.ac.uk/), through the utility [Molden](http://www.cmbi.ru.nl/molden/). See [molden_gabedit.jpg](https://raw.githubusercontent.com/zorkzou/Molden2AIM/master/molden_gabedit.jpg).
* [MOLCAS](http://www.teokem.lu.se/molcas/)
* [MOLPRO](http://www.molpro.net/)
* [MRCC](http://www.mrcc.hu/)
* [NBO6](http://nbo6.chem.wisc.edu/) (> May.2014)
* [NWChem](http://www.nwchem-sw.org/), through the [JANPA/nwchem2molden](http://janpa.sourceforge.net/) script
* [ORCA](https://orcaforum.cec.mpg.de/)
* [Priroda](http://wt.knc.ru/wiki/index.php/Priroda_Documentation)
* [PSI4](http://www.psicode.org/)
* [Q-Chem](http://www.q-chem.com/)
* [TeraChem](http://www.petachem.com/)
* [Turbomole](http://www.turbomole.com/)

See [readme.html](http://zorkzou.github.io/Molden2AIM/readme.html) for details.

Examples of applications can be found in W. Zou, D. Nori-Shargh, and J. E. Boggs, On the Covalent Character of Rare Gas Bonding Interactions: A New Kind of Weak Interaction, J. Phys. Chem. A, 2013, 117(1), pp 207-212 at http://pubs.acs.org/doi/abs/10.1021/jp3104535
