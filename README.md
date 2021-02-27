# strong-wrapper
SMAC is a very powerful tool for optimizing parameters for an algorithm.
However, to optimize these parameters you need a good wrapper.
This is also discussed in great detail in [this article](https://ai.dmi.unibas.ch/research/reading_group/eggensperger-et-al-jair2019.pdf)
Essentially, a wrapper with poor performance can make or break the outcome of parameter configuration.

During my 5th semester project where we worked in a group with ant colony optimization I developed this wrapper.
The wrapper was developed solely for the purpose of using SMAC alongside our algorithm, and since the wrapper we had before showed poor performance, I named this wrapper "strong-wrapper".

The wrapper is written in python, since it only seemed natural, since the version of SMAC we used was also written in python.
If you found this repository then I assume that you are already familiar with SMAC, its use cases, and how to invoke it from the command line.

## Preliminaries
If you want to use this wrapper you will have to change a little bit in the code.
If you want to use the wall clock limit functionality then you will have to make your algorithm print its results, whenever it finds a new one.
Keep in mind, using the wall clock limit is highly algorithm specific, so be careful when using it.

## How to use this
Inside `tester.py` you will find a small example of how it can be used.
Our algorithm was written in C++, so that is why we had to call the binary file "routeplanner".
If your algorithm is also a binary, then you may do this in a similar fashion, alongside setting static parameters.
If your algorithm is written in python you may tweak this code to invoke the algorithm directly, or you may invoke it in a similar fashion using a shebang line in your algorithm.

The set of dynamic parameters are set within `strongwrapper.py` itself in the `commandBuilder` function.

The GetScore function may also be overwritten to fit your needs.
