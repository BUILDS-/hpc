# HPL Install instructions

We followed the INSTALL file and used the following commmand

	make arch=x86

This gave us an error so we needed to add to the `Make.x86` file the following `CCFLAG`

	-pthread

To test we ran the following in the `/nfs/hpl-2.1/bin/x86`

	mpirun -np 4 ./xhpl
	





