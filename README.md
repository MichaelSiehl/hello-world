# MPMD with Fortran 2008 Coarrays Repository

# Important Update (16/10/04)
Please be aware that the original source code in the 'src' folder is not conforming with the Fortran (2008/2015) standard since it does not use any Fortran (2008) means for the synchronizations (between coarray images) in the MPMD-style part of the source codes.<br />
I just added a new source code folder 'src_atomic_version', containing a very similar example program which does utilize Fortran 2008 SYNC MEMORY and atomic subroutines. Within that new version of the example program the SYNC MEMORY statements do form unordered execution segments (see Modern Fortran explained, 2011, Appendix B.10.1 for a brief description). To compile that code you may need a more recent Fortran compiler since the code uses scalar integer components of derived type coarrays together with atomic subroutines (atomic_define, atomic_ref) (ifort 15 did not allow this, while ifort 17 as well as gfortran7/OpenCoarrays do allow it).<br />
Compared to the original src version, the source code of the new src_atomic_version contains only very few changes which are marked with '160829' and '160901' comments (time stamps).

# Overview
This Repository is dedicated to a programming style that allows MPMD(Multiple-Program Multiple-Data)-like parallel programming using Fortran 2008 Coarrays (PGAS). Most of the files herein were firstly published on the website www.mpmd-with-coarray-fortran.de. The example code of this Repositiry is intented to be the first one in a series of follow-up examples and is probably the most simple one, hopefully suitable as an entry level to others.

Our programming style is object-based, using Fortran 95 style Abstract Data Types (ADT). Thus, you should have some Fortran 95 coding experiences as well as some basic object-based programming experiences. A basic knowledge of parallel programming with coarrays is also required. 

To start, you should read the short paper 'MPMD with Coarray Fortran (2008): an Example Program' (pdf format) in the Repositorys main folder or at http://www.mpmd-with-coarray-fortran.de/MPMD_with_Coarray_Fortran_2008.pdf. Chapter 2 may serve as a first preparation to understand the MPMD example program, whereas chapter 3 explains the example program in more detail.
