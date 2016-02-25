# hpcg

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

### huyrocksmysox
We based our makefile off Make.Linux_MPI from the hpcg-3.0 source. We copied it as Make.huyrocksmysox. To customize, we linked the MPI libraries properly as they were configured on the 6 node cluster.

### Install/Setup Instructions
We first downloaded the tar source into our NFS folder on our MPI enabled 6 node cluster. After extracting the source, we used the following commands for setup:

```
cd hpcg-3.0/
mkdir build
cp ../hpc/hpcg/Make.huyrocksmysox setup/
cd build/
/nfs/hpcg-3.0/configure huyrocksmysox
make
```

### Performance
Mesh sizes must be divisible by 8.

| Cluster       | Version       | Mesh Size   | Cores | GFLOP/s |
|---------------|---------------|-------------|-------|---------|
| 6 x86 nodes   | 3.0 Source    | 104         | 6     | 1.31751 |
| 6 x86 nodes   | 3.0 Source    | 16          | 4     | 1.17194 |
| 6 x86 nodes   | 3.0 Source    | 16          | 6     | 2.3234  |
| 6 x86 nodes   | 3.0 Source    | 16          | 24    | 3.38351 |
| 6 x86 nodes   | 3.0 Source    | 32          | 24    | 3.43043 |
| 6 x86 nodes   | 3.0 Source    | 48          | 24    | 3.44794 |
| 6 x86 nodes   | 3.0 Source    | 56          | 24    | 3.44749 |


