# A Simple Determinant Quantum Monte Carlo (DQMC) code

### Brief introduction

This a simple Determinant Quantum Monte Carlo (DQMC) code for international summer school on computational approaches for quantum many body systems. (http://compqmb2016.csp.escience.cn)
We take Hubbard model on square lattice as an example, showing how DQMC simulation works.

### How to use it?

It is very easy to compile this code, you only need a Fortran compiler.
Here are steps to compile and run the code in Linux system.
By default, we will use gfortran to compile it.

1. download the code package and decompress it.
assume you have put the code in directory repodir

2. compile the library
cd repodir/lib
make

3. compile the source code
cd repodir/src
make

4. run the code
cd repodir/run
edit the parameters you want to calculate in cal_para.sh
./run.sh >logs 2>&1 &

5. analysis data
When the simulation is finished, you can analysis data using the available script in directory results
If you want to analysis the dynamical Green function, you need first compile a utility in analysis to compute covariance.
cd repordir/analysis
make

In directory results/benchmark, there are some data for benchmark.

For Windows users, you can use visual studio to compile it.
But you can not use the available scripts to run the code and analysis results automatically.
So I strongly suggest you to install a Linux system.

