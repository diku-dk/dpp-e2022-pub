# Data Parallel Programming (DPP), Block 2 2022

## Nvidia Acknowledgements

We are grateful to Nvidia for awarding us a teaching grant (for the PMPH and DPP courses) that consists of two A100 GPUs. These are now accessible on the server futharkhpa03fl.unicph.domain


## Course Structure

DPP is structured around five weeks with lectures and lab sessions
on Monday and Wednesday, followed by a final project to be
presented orally at the exam.  Throughout the course, you will hand in
four weekly assignments.  These *weeklies* count for 40\% of the
grade, while the exam counts for 60\%.

The teachers are **Cosmin Oancea** and **Troels Henriksen**.

All lectures and lab sessions will be delivered in English.  The
assignments and projects will be posted in English, and while you can
chose to hand in solutions in either English or Danish, English is
preferred.

All course material is distributed via this GitHub page.  Assignment
handin is still on Absalon.  There is no mandated textbook for the
course - you will be assigned reading material from papers and such.

## Course schedule

[Course Catalog Web Page](https://kurser.ku.dk/course/ndak21006u/2022-2023)

### Lectures (zoom links will be posted on Absalon):

* Monday    13:00 - 15:00 (weeks 47-51, 1-3	in aud - Aud 03 AKB, Universitetsparken 13)
* Wednesday 10:00 - 12:00 (weeks 47-51, 1-3	in aud - Aud 02 AKB, Universitetsparken 13)

### Labs:

* Monday 15:00 - 17:00 (weeks 47-51, 1-3, in øv - NBB 01.1.H.142, Jagtvej 155)
* Wednesday 13:00 - 15:00 (weeks 47-51, 1-3, in øv - 4-0-13, Ole Maaløes Vej 5, Biocenter)

[Location of lectures and labs](https://skema.ku.dk/tt/tt.asp?SDB=ku2223&language=EN&folder=Reporting&style=textspreadsheet&type=student+set&idtype=id&id=182716&weeks=1-53&days=1-7&periods=1-68&width=0&height=0&template=SWSCUST+student+set+textspreadsheet)

The current plan is that everybody will have a physical place
at the lecture and lab. Unless we are forced to move to virtual
teaching, the lectures and labs will not be recorded, so please
plan to attend (albeit, if there is a strong request, we may
zoom them online).


This course schedule is tentative and will be updated as we go along.
**The schedule below will become the correct one as you enter the
week when the course starts.**

The lab sessions are aimed at providing help for the weeklies and
group project.  Do not assume you can solve them without showing
up to the lab sessions.

[Zoom link for lectures](https://ucph-ku.zoom.us/j/67002083301?pwd=SjdGdlZmRllXMEd1VVcxU0p6QlR1Zz09)

### Lecture plan

| Date | Time | Topic | Material |
| --- | --- | --- | --- |
| 21/11 | 13:00-15:00 | [Intro, deterministic parallelism, data parallelism, Futhark](slides/L1-determ-prog.pdf) | [Parallel Programming in Futhark](https://futhark-book.readthedocs.io/en/latest/) | |
| 21/11 | 15:00-17:00 | Lab | [Futhark exercises](bootstrap-exercises.md) | |
| 23/11 | 10:00-12:00 | [Cost models, advanced Futhark](slides/L2-advanced-futhark-cost-models.pdf) | [Guy Blelloch: Programming Parallel Algorithms](material/blelloch-programming-parallel-algorithms.pdf), [Prefix Sums and Their Applications](material/prefix-sums-and-their-applications.pdf), [A Provable Time and Space Efficient Implementation of NESL](material/a-provable-time-and-space-efficient-implementation-of-nesl.pdf) |
| 23/11 | 13:00-15:00 | Lab ([**Assignment 1 handout**](weekly-1/)) | |
| 28/11 | 13:00-15:00 | [List homomorphisms](slides/L3-list-homomorphisms.pdf) | [The Third Homomorphism Theorem](material/algorithms/lhomo-third-theorem.pdf), [Construction of List Homomorphisms by Tupling and Fusion](material/algorithms/lhomo-tupling.pdf) |
| 28/11 | 15:00-17:00 | Lab | |
| 30/11 | 10:00-12:00 | [Vector programming with ISPC](slides/L4-ispc.pdf) | [ispc: A SPMD Compiler for High-Performance CPU Programming](material/ispc_inpar_2012.pdf) | |
| 30/12 | 13:00-15:00 | Lab ([**Assignment 2 handout**](weekly-2/)) | |
| 05/12 | 13:00-15:00 | [Full/irregular flattening](slides/L5-irreg-flattening.pdf) | [PMPH lecture notes, Chapter 4](material/flattening/lecture-notes-pmph.pdf), [Transforming High-Level Data-Parallel Programs into Vector Operations](material/flattening/NeslFlatTechPaper.pdf), [Harnessing the Multicores: Nested Data Parallelism in Haskell](material/flattening/harnessing-multicores.pdf) (not easy to read)|
| 05/12 | 15:00-17:00 | Lab | |
| 07/12 | 10:00-12:00 | [Full/irregular flattening](slides/L5-irreg-flattening.pdf) | [PMPH lecture notes, Chapter 4](material/flattening/lecture-notes-pmph.pdf), [Transforming High-Level Data-Parallel Programs into Vector Operations](material/flattening/NeslFlatTechPaper.pdf), [Harnessing the Multicores: Nested Data Parallelism in Haskell](material/flattening/harnessing-multicores.pdf) (not easy to read)|
| 07/12 | 13:00-15:00 | Lab ([**Assignment 3 handout**](weekly-3/)) | |
| 12/12 | 13:00-15:00 | [Polyhedral Analysis](slides/L8-polyhedral.pdf) | [PMPH Dependence Analysis](material/poly/L5-LoopParI.pdf); [Sven Verdoolaege: Presburger Formulas and Polyhedral Compilation (tutorial)](material/poly/polycomp-tutorial.pdf); [Sven Verdoolaege: Presburger Sets and Relations: from High-Level Modelling to Low-Level Implementation (slides)](material/poly/poly-in-detail.pdf), [Code Examples](material/poly/poly-code-egs/) |
| 12/12 | 15:00-17:00 | Lab | |
| 14/12 | 10:00-12:00 | [Regular and incremental flattening](slides/L8-regular-flattening.pdf) | [Futhark: Purely Functional GPU-Programming with Nested Parallelism and In-Place Array Updates](https://futhark-lang.org/publications/pldi17.pdf),  [Incremental Flattening for Nested Data Parallelism](https://futhark-lang.org/publications/ppopp19.pdf) (particularly the latter), **Optional:** [Dataset Sensitive Autotuning of Multi-Versioned Code based on Monotonic Properties](https://futhark-lang.org/publications/tfp21.pdf) |
| 14/12 | 13:00-15:00 | Lab ([**Assignment 4 handout**](weekly-4/)) | |
| 19/12 | 13:00-15:00 | [Data-parallel automatic differentiation](slides/L9-AD.pdf) | [Automatic Differentiation in Machine Learning: a Survey, Baydin et. al.](material/automatic_differentiation_in_ml_baydin.pdf), [autodiff.fut](material/autodiff.fut) [AD for an Array Language with Nested Parallelism](material/ad-sc22/pdf) |
| 19/12 | 15:00-17:00 | Lab | |
| 21/12 | 10:00-12:00 | [Data-parallel automatic differentiation](slides/L9-AD.pdf) | same material as previous lecture |
| 21/12 | 13:00-15:00 | Lab (with project proposals) | |

After New Years, *maybe* there will be no lectures (we are still thinking on it),
but labs will still be held to help with the group project.

| Date | Time |
| ---  | ---  |
| 02/1 | 15:00-17:00 |
| 04/1 | 13:00-15:00 |
| 09/1 | 15:00-17:00 |
| 11/1 | 13:00-15:00 |

## Weekly assignments

The weekly assignments are **mandatory**, must be solved
**individually**, and make up 40% of your final grade.  Submission is
on Absalon.

You will receive feedback a week after the handin deadline (at the
latest).  You then have another week to prepare a resubmission.  That
is, **the resubmission deadline is two weeks after the original handin
deadline**.

The assignment text and handouts will be linked in the schedule above.

## Group project and exam

The final project, along with the exam as a whole, contributes 60% of
your grade, and is done in groups of 1-3 people (although working
alone is strongly discouraged).  We have [a list of project
suggestions](project-suggestions.md), but you are free to suggest your
own (but please talk with us first).  Since the time to work on the
project is rather limited, and there is no possibility of
resubmission, you should ask for help early and often if you are
having trouble making progress.  **The project should be handed in via
Absalon on Friday the 21st of January**.  Send an email if you have
trouble meeting this deadline.

Most of the projects are about writing some parallel program, along
with a report describing the main points and challenges of the
problem.  The exam format is a group presentation followed by
individual questions about both your project **and anything else in
the curriculum**.  Each group prepares a common presentation with
slides, and each member of the group presents non-overlapping parts of
the presentation for about 10 min (or less). Then each member of the
group will answer individual questions for about 10 min.

## Practical information

You may find it useful to make use of DIKUs GPU machines in your work.

To connect you need one of the following:

* Be [connected to the KU VPN](https://github.com/diku-dk/howto/blob/main/vpn.md)

* Be physically connected to the *wired network* at DIKU.

Once this is done, you can access the GPU machines by SSH'ing to the
following hosts:

* `futharkhpa01fl.unicph.domain`

* `futharkhpa02fl.unicph.domain`

* `futharkhpa03fl.unicph.domain`

Log in with your usual KU login information.

All machines should have all the software installed you need.  If you
are missing something, [contact Troels](mailto:athas@sigkill.dk).  The
first and last machine has NVIDIA A100 GPUs, and the second machine
has an AMD MI100 GPU.

Consider using
[sshfs](https://www.digitalocean.com/community/tutorials/how-to-use-sshfs-to-mount-remote-file-systems-over-ssh)
to mount the remote file system on your local machine:

```
$ mkdir remote
$ sshfs futharkhpa01fl.unicph.domain: remote
```

### GPU setup

For CUDA to work, you may need to add the following to your `$HOME/.bash_profile`:

```bash
export CPATH=/opt/rocm/opencl/include:/usr/local/cuda/include:$CPATH
export LIBRARY_PATH=/opt/rocm/opencl/lib:/usr/local/cuda/lib64:$LIBRARY_PATH
export LD_LIBRARY_PATH=/opt/rocm/opencl/lib:/usr/local/cuda/lib64:$LD_LIBRARY_PATH
```

## Other resources

You are not expected to read/watch the following unless otherwise
noted, but they contain useful and interesting background information.

* [The Futhark User's Guide](https://futhark.readthedocs.io), in
  particular [Futhark Compared to Other Functional
  Languages](https://futhark.readthedocs.io/en/latest/versus-other-languages.html)

* [Troels' PhD thesis on the Futhark compiler](https://futhark-lang.org/publications/troels-henriksen-phd-thesis.pdf)

* [A library of parallel algorithms in NESL](http://www.cs.cmu.edu/~scandal/nesl/algorithms.html)

* [Functional Parallel Algorithms by Guy Blelloch](https://vimeo.com/showcase/1468571/video/16541324)

* ["Performance Matters" by Emery Berger](https://www.youtube.com/watch?v=r-TLSBdHe1A)

* [The story of `ispc`](https://pharr.org/matt/blog/2018/04/18/ispc-origins.html) (you can skip the stuff about office politics, although it might ultimately be the most valuable part of the story)

* [Scientific Benchmarking of Parallel Computing
  Systems](https://htor.inf.ethz.ch/publications/img/hoefler-scientific-benchmarking.pdf)
  (we benchmark much simpler systems and don't expect anywhere near
  this much detail, but it's useful to have thought about it)
