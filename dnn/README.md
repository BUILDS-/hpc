# DNN

To run:
	
	sh train.sh

Results are logged to `mlp.0.log`:

| Optimization | Running Speed |
| --- | --- |
| None | 383427.000000ms |

There are two branches:

* **dnntk_src**
	This is the training code
* **dnn_cvtk_src**
	Validation code

## Optimizations

#### Compiler Change
We changed the compiler from the line:

	GCC = g++

To:

	GCC = icc

To better take advantage of the intel compiler optimizations.

#### MPI Paralellization

To come...

More explanation can be found here: http://asc-events.org/ASC16/Preliminary.php
 

