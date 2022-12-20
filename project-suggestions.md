# Project suggestions

These projects are intentionally open-ended.  They are intended as an
opportunity for you to showcase your mastery of the learning goals:

* Parallel algorithmic reasoning.

* Parallel cost models.

* Judging the suitability of the language/tool for the problem at
  hand.

* Applied data-parallel programming.

This means that you are free to diverge from the project descriptions
below, or come up with your own ideas, as long as they provide a
context in which you can demonstrate the course contents.

You are *not* judged on whether e.g. Futhark or ISPC or whatever
language you choose happens to be a good fit or run particularly fast
for whatever problem you end up picking, but you *are* judged on how
you evaluate its suitability.

## Parallelising multiple precision arithmetic

Machines tend to support only numbers of some fixed precision, such as
32 or 64 bits.  Larger numbers must be implemented in software.  Some
domains, such as cryptography, involved numbers that are much larger
than what is directly supported by machines.  While there is perhaps
not much need for parallelising 128-bit arithmetic, operations on much
larger numbers may be worth parallelising.  For example, a scan can be
used to implement addition (see [this Blelloch
paper](material/prefix-sums-and-their-applications.pdf)).

This project is about implementing, in Futhark, a small library for
multiple precision integer arithmetic.  The goal is to handle integers
of any *fixed* user-provided size (that is, not full
arbitrary-precision).  Addition, subtraction, and multiplication
should be straightforward.  Division is likely also doable.  Depending
on time and interest, you can move on from there.

For inspiration and performance comparison:

* [The CGBN library for CUDA](https://github.com/NVlabs/CGBN)

* [The GNU Multiple Precision Arithmetic Library](https://gmplib.org/)

## Porting a Parboil benchmark to a parallel language

[Parboil](http://impact.crhc.illinois.edu/parboil/parboil.aspx) is a
suite of benchmarks that is used when presenting new research into
compilers or parallel programming.  This project is about picking one
of the benchmarks and porting it to a parallel language covered in
class (I prefer Futhark, but if you want to use `ispc` or Parallel
Haskell, that's fine too).  For Futhark, [we already have
implementations of `histo`, `mri-q`, `sgemm`, `stencil`, and
`tpacf`](https://github.com/diku-dk/futhark-benchmarks/tree/master/parboil),
so we are mostly interested in the remaining ones.  In particular, we
have an interest in the `lbm` benchmark.

## Porting PBBS benchmarks

The [Problem Based Benchmark
Suite](https://cmuparlay.github.io/pbbsbench/) is a collection of
benchmark programs written in parallel C++.  We are interested in
porting them to a high-level parallel language (e.g. Futhark).  Some
of the benchmarks are relatively trivial; others are more difficult.
It might be a good idea for a project to combine a trivial benchmark
with a more complex one.  The [list of benchmarks is
here](https://cmuparlay.github.io/pbbsbench/benchmarks/index.html).
The ones listed as *Basic Building Blocks* are all pretty
straightforward.  Look at the others and pick whatever looks
interesting (but talk to us first - some, e.g. rayCast, involve no
interesting parallelism, and so are not a good DPP project).

## Flattening a Batch of Rank-Search-k Problems

Please see [Rank-Search-k project presentation.](group-projects/rank-search-k/Project-RankSearch-k.pdf)

The fastest way of sorting that we know of is by using [Cuda's CUB library](group-projects/cub-code). You may adapt the code to sort a batch of (irregular) arrays and use that as a baseline for comparison. 

## QR Decomposition/Factorization

We are interested in developing efficient implementation(s) for QR decomposition
in a high-level parallel language (Futhark). You are supposed to do a quick literature
search and find suitable implementations, and then to pick a "reasonably-complex" one,
implement it in Futhark and report a systematic performance evaluation, e.g., you can use
as baseline Cublas' implementation and report performance in GFlops/sec.

A very quick google search has revealed several related papers, for example
[QR Decomposition on GPUs, 2009](group-projects/QR-decomposition/QR-decomp-GPU.pdf) and
[Implementing QR factorization updating algorithms on GPUs](group-projects/QR-decomposition/QR-fact-updates-GPU.pdf).

## Translating a Mpack-2 benchmark to Futhark and using AD to show the Jacobian-sparsity pattern

This project refers to translating *one* of the benchmarks from the "MINPACK-2 test problem collection" (from Fortran) to Futhark and then using Futhark's AD support to compute the Jacobian of the objective function and to display the sparsity pattern of the Jacobian.

[Here is where you find the Fortran code for the "MINPACK-2 test problem collection"](https://github.com/jacobwilliams/MINPACK-2/tree/master/tprobs). There is a README at that location, please read it to understand which files implement what problem. Once you have found the proper files, please remember that you need to translate to Futhark only the "objective function", i.e., the Fortran implementation also computes (by hand) the gradient/Jacobian, sparsity pattern and other things.

[Here is an article presenting the "MINPACK-2 test problem collection"](group-projects/Mpack-2/Minpack-2.pdf).

[Here is another article that analyses the sparsity of several MINPACK-2 problems, specifically, flow in a driven cavity (FDC), flow in a channel (FIC), incompressible elastic rod (IER), swirling flow between disks (SFD), solid fuel ignition (SFI)](group-projects/Mpack-2/Efficient_Computation_of_Gradients_and_Jacobians_b.pdf)


## Implementing full flattening in the Futhark compiler

We are currently working on implementing full flattening in the
Futhark compiler.  [The current state of the implementation can be
seen
here.](https://github.com/diku-dk/futhark/blob/flattening/src/Futhark/Pass/Flatten.hs).
The current implementation is very incomplete, but can handle some
programs.  This project is about implementing *simple* missing cases
in the flattening transformation.  Ideas (one of these is probably
enough):

* The general case of slicing is implemented, but one could implement
  a more efficient version of the case where the *size* is invariant
  to the `map` and only offset/stride is variant.

* Implementing segmented transpose.

* Implementing segmented update.

* Implementing segmented concat.

This project involves hacking on the actual Futhark compiler, which is
written in Haskell.  Further, it is designed to be a *good compiler*,
rather than to be immediately accessible to students.  However, you
can expect significant help in figuring out the compiler side of
things.  This is a *tricky* project, which is why what is expected of
you is relatively small.  You might start by first implementing (in
normal Futhark) an example of the code you want, and then afterwards
implementing it in the compiler.

This kind of project is most interesting to people who wish to do more
Futhark-related projects later in their studies.

## Implementing NPB-EP and NPB-CG

Implement the EP and CG benchmarks from [NAS Parallel
Benchmarks](https://www.nas.nasa.gov/software/npb.html) in Futhark and
use them to perform a measurement of Futhark's performance portability
[as in this
paper](https://link.springer.com/article/10.1007/s10766-022-00746-1).
