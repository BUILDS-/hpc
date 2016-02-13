#  TX1: 256 Maxwell cores + ARMv8 A57 quad core 2 level cache
#### Here are the arm based benchmarks and applications for an ARM based system for ISC'16 running on a Tegra TX1 in preparation for a true ARM + CUDA based hpc  system.

## Linpack (hpl)
There two different versions of linpack compiled: one is cpu based and the other is gpu based. The cpu based makefile is `Make.arm` and a run of the benchmark results is located in `hpl-2.1/bin/arm/`. We need to optimize the inputs. 
The second version of linpack, cuda linpack, is the fermi (microarchitecture) based Nvidia GPU. This is the only one I could find, but it was used on Tesla based GPUs on k40m and k20 in previous SCCs. I was able to compile, but I get pinned memory errors. My guess is the TX1 is a unified memory access system, whereas the cuda linpack was written for non unified memory access. We need to look at the code and change some of the cuda memory api calls.

## HPCC
HPCC is compiled for arm. I wonder if there's a cuda version. Make file for hpcc is almost the same as hpl, with slight modifications to the top directory (Topdir) to point one level deeper in hpcc for hpl. Results are `hpccoutf.txt` and input file is `hpccinf.txt` on the top level of hpcc. The makefile, `Make.arm` is also located here. 
There was a small change to get the STREAM benchmark to work. I had to get rid of the  `restrict` keywords in the line with `double * restrict a, * restrict b, * restrict c;`. Our compiler didn't need this. 
I also downloaded a mpi version, `stream_mpi.c` to test later. 
