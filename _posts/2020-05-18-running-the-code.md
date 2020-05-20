---
layout: post
title: "MATH 4391: Running the code"
---

> # Zoom Meeting Notes
>
> ## More info on the code 
> "Reduction of a vector" - means to take out the zeros
> > Q: Vectors? Runtime? Recursion?
>
> Sparse storage and memory
> Storing sparse symmetric matrices
> Sparse array
> Indexing formulas - lemma and proof by induction
> Q: "Nsp" How do we estimate the max number of non-zero indices for efficient storage?
> Random binomial distribution
> > The values of n entries in an array follow binomial distribution.
> NPshift
>
> ## Using CUPy
> CUPy easily throws out the zero entries with cupy.flatnonzero()
> > What is the run time for this?
> Importing libraries: numpy and cupy
> > numpy (np) used for numerical notation
> > cupy (cp) used for parallel programming
> Functions in the code:
> > cp.random.choice (from population of n size, choose a random number with replacement)
> > cp.put ( all infected children, initial index)
> > cp.ones ( add a 1 to the zero value and the index to indicate infected household)
> > cp.arange (64 bit ints)
> > cp.asscalar
> 32 bit integers vs 64 bit integers
> > dtype=cp.int32
> unsigned long int
>
> ## More info on parallel computing
> CUDA multithreading
> Cores, threads, blocks of threads on a grid
> > Q: How do grids work?
> (x,y,z)
> Storing chunks of a matrix
> N(N-1)/2 and where it comes from
> Kernel functions - using C/C++
> 
> ## Issues
> GPU (Device) & CPU (Host)
> > Sending things between the host and the device takes time and we want to keep it all in one place.
> Overflow errors when indices are very large (64 bit integers)
> > Everything in 64 bit increases the storage needed
>
### Questions  ###
> Defining a subroutine?
> just-in-time compilation
> Understand nzc
> device arrays .get()
> array indexing in C++ vs python
> Is it possible to do away with the need to shift? Understanding the use of NPshift
> > How do we continue using it? What are the alternatives? Consequences of each?
> Define the use of NPiter
>
### Further reading to-do  ###
> <a href="https://pure.strath.ac.uk/ws/portalfiles/portal/7357442/fastbalance.pdf">Knight, Philip ; Ruiz, Daniel. / A fast algorithm for matrix balancing. In: IMA Journal of Numerical Analysis. 2013 ; Vol. 33, No. 3. pp. 1029-1047.</a>

> <a href="http://www0.cs.ucl.ac.uk/staff/wlangdon/ftp/papers/langdon_2010_cigpu.pdf">Evolving a CUDA Kernel from an nVidia Template by W. B. Langdom and M. Harman</a>

> <a href="https://bib.irb.hr/datoteka/586501.CUDA_SIR_Sosic_Sikic_final.pdf">Sosic, Matija and Mile Šikić. “CUDA implementation of the algorithm for simulating the epidemic spreading over large networks.” 2012 Proceedings of the 35th International Convention MIPRO (2012): 1807-1810.</a>

>  <a href="https://www.semanticscholar.org/paper/CuPy-%3A-A-NumPy-Compatible-Library-for-NVIDIA-GPU-Okuta-Unno/a59da4639436f582e483347a4833e7659fd3e598">Okuta, Ryosuke et al. “CuPy : A NumPy-Compatible Library for NVIDIA GPU Calculations.” (2017).</a>
> > <a href="https://github.com/cupy/cupy">Github</a>

> A Sparse Matrix Library in C++ for High Performance Architectures by Jack Dongarraxz, Andrew Lumsdaine, Xinhiu Niu, Roldan Pozoz, and Karin Remingtonx</a>
> <a href="https://wwwuser.gwdg.de/~parallel/parallelrechner/scalapack/lawns/lawn74.pdf">Sparse Matrix Libraries for C++</a>

> <a href="http://jefftrull.github.io/c++/eigen/csparse/suitesparse/2017/02/09/sparse-matrices-for-cplusplus.html">Working with Sparse Matrices</a>

> <a href="https://www.mathcs.emory.edu/~cheung/Courses/561/Syllabus/3-C/sparse.html">Generic Parallel Algorithms for Sparse Matrix and Graph Computations (cusp-library)</a>

> <a href="https://code.google.com/archive/p/cusp-library/">cusp-library</a>
> 
### Emacs keyboard shortcuts   ###
> <a href="http://www.rgrjr.com/emacs/emacs_cheat.html">This</a> is a link to Dave Cohen's emacs cheat sheet.
> * Always use ESC-x linum-mode during screen sharing.
>