# hpcg

### Cluster
We are using a 6 node cluster. Each node has 4 Intel(R) Xeon(R) CPU 5140 @ 2.33 GHz processors with no accelerators.

### Version
For the 6 node cluster, we are using base version of HPCG - 3.0

```
cd /nfs
wget http://www.hpcg-benchmark.org/downloads/hpcg-3.0.tar.gz
tar -xvf hpcg-3.0.tar.gz
```

### Makefile

### huyrocksmysox
We based our makefile off Make.Linux_MPI from the hpcg-3.0 source. We copied it as Make.huyrocksmysox. All we did was link the MPI libraries properly as they were configured on the 6 node cluster.

### Install/Setup Instructions
We first downloaded the tar source into our NFS folder on our MPI enabled 6 node cluster. After extracting the source, we:

```
cd hpcg-3.0/
mkdir build
cp ../hpc/hpcg/Make.huyrocksmysox setup/
cd build/
/nfs/hpcg-3.0/configure huyrocksmysox
make
```

### Performance

#### 6 Node Cluster - No Accelerators - Ethernet - 24 cores
16 x 16 x 16 mesh - 1 Gigaflop
