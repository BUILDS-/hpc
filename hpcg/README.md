# hpcg

### Run

```
mpirun -n 24 -f /root/nfs/hosts ./xhpcg --nx=16 --rt=3600
```

### Cluster Specs

| Cluster       | CPU                                   | Cores | Accelerator  |
|---------------|---------------------------------------|-------|--------------|
| 6 x86 nodes   | Intel(R) Xeon (R) CPU 5140 @ 2.33 GHz | 4     | None         |


### Version

| Cluster       | Version       |
|---------------|---------------|
| 6 x86 nodes   | 3.0 Source    |

```
# Download and extract instructions
cd /nfs
wget http://www.hpcg-benchmark.org/downloads/hpcg-3.0.tar.gz
tar -xvf hpcg-3.0.tar.gz
```

### Makefile

### MPI
We based our makefile off Make.Linux_MPI from the hpcg-3.0 source. We copied it as Make.MPI. To customize, we linked the MPI libraries properly as they were configured on the 6 node cluster.

### Install/Setup Instructions
We first downloaded the tar source into our NFS folder on our MPI enabled 6 node cluster. After extracting the source, we used the following commands for setup:

```
cd hpcg-3.0/
mkdir build
cp ../hpc/hpcg/Make.MPI setup/
cd build/
/nfs/hpcg-3.0/configure MPI
make
```

### Benchmarking Performance - 60 seconds
Mesh sizes must be divisible by 8.

| Cluster       | Version       | Mesh Size   | Cores | GFLOP/s | Type        |
|---------------|---------------|-------------|-------|---------|-------------|
| 6 x86 nodes   | 3.0 Source    | 104         | 6     | 1.31751 | MPI         |
| 6 x86 nodes   | 3.0 Source    | 16          | 4     | 1.17194 | MPI         |
| 6 x86 nodes   | 3.0 Source    | 16          | 6     | 2.3234  | MPI         |
| 6 x86 nodes   | 3.0 Source    | 16          | 24    | 3.44749 | MPI         |
| 6 x86 nodes   | 3.0 Source    | 16          | 24    | 3.39781 | MPI_OPENMPI |
| 6 x86 nodes   | 3.0 Source    | 24          | 24    | 3.10402 | MPI_OPENMPI |
| 6 x86 nodes   | 3.0 Source    | 32          | 24    | 3.02452 | MPI_OPENMPI |
| 6 x86 nodes   | 3.0 Source    | 48          | 24    | 2.31746 | MPI_OPENMPI |
| 6 x86 nodes   | 3.0 Source    | 112         | 24    | 2.815   | MPI_OPENMPI |

### Benchmarking Performance - 1 hour

| Cluster       | Version       | Mesh Size   | Cores | GFLOP/s | Type        |
|---------------|---------------|-------------|-------|---------|-------------|
| 6 x86 nodes   | 3.0 Source    | 16          | 24    | 3.48752 | MPI_OPENMPI |
