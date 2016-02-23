# DNN

To run, run:
	
	sh train.sh

We're putting results in a `output_file`:

	sh train.sh > output_file &

Then we get output in `mlp.0.log`

There are two branches:

* **dnntk_src**
	This is the training code
* **dnn_cvtk_src**
	Validation code

We change the compiler from the line:

	GCC = g++

To:

	GCC = icc

To better take advantage of the intel compiler optimizations.

More explanation can be found here: http://asc-events.org/ASC16/Preliminary.php
 

