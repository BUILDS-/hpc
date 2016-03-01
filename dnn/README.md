# DNN

To run:
	
	sh train.sh

Results are logged to `mlp.0.log` and `mlp_cv.0.log`.

| Optimization | Running Speed | Percent Increase |
| --- | --- | --- |
| None | 421780.000000ms | 0% |
| Intel Compiler | 383427.000000ms | 10% |

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
 

