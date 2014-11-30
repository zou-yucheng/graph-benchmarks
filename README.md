graph-benchmarks
================

This directory contains directed graph benchmarks in DIMACS graph
format. These graphs were mainly used to evaluate optimum cycle
mean/ratio algorithms in multiple of my papers on the subject. 

You can of course use these graphs to run my programs under
'optimum-cycle-ratio-algorithms' or 'optimum-cycle-mean-algorithms'
under 'github/alidasdan'.

Most of these graphs are from existing benchmarks or from other
research papers or books. Many under core were generated by me to
debug my own code. See [Da04] and my other publications on optimum
cycle ratio and mean algorithms to learn more about the use of these
benchmarks.

Here are the files and subdirectories and information about their content:

```
all-max-runs.txt -- generated as detailed in runs.how

all-min-runs.txt -- generated as detailed in runs.how

core/ -- small graphs that were extremely useful to debug my own code

core-bad/ -- subgraphs from iscas that revealed infinite loops in some programs

core-big/ -- slightly larger graphs similar to those under core

ibm/ -- graphs generated from ibm circuit benchmarks

iscas/ -- graphs generated from iscas circuit benchmarks

random/ -- randomly generated graphs to match the sizes of the corresponding ibm graphs

runs.how -- runs of optimum cycle ratio algorithms

scripts/ -- scripts to manipulate various parameters of these graphs

tests/ -- tiny graphs to use as first tests
```

### DIMACS GRAPH FORMAT

The input file format is the DIMACS format. See the file
tests/sample.d for a sample input file, which is also explained below.

```
> cat sample.d
p sample-253926760 4 7
a 1 2 40 9
a 2 1 60 17
a 2 3 50 8
a 3 1 30 24
a 4 3 60 22
a 2 4 70 14
a 4 1 30 20
```

Here the 'p' line (the 'problem' line) states that our graph, named
'sample', has 4 nodes or vertics and 7 arcs or directed edges. The arc
weights are generated from a (usually uniform) random number generator
initialized by a seed of '253926760'.

The 'a' lines (the 'arc' lines) following the 'p' line list each arc
as from a source node to a target node with two integer weights: an
arc weight followed by a transit time. For example, the first 'a' line
indicates an arc from node '1' to node '2' with a weight '40' and a
transit time '9'. Note that the node ids start from 1 instead of 0.

For cycle mean algorithms, the transit time is ignored or can be
thought of as equal to '1'. Any lines marked with a 'c' is a comment.

The file sample.pdf (generated from sample.dot using the dot tool in
the graphviz package) shows a picture of the graph in sample.d.

You can use the scripts under
'github/alidasdan/graph-benchmarks/scripts' to change the arc weights,
e.g., regenerate using different random number generator seeds or
using different distributions.

### REFERENCE

Please cite this reference if you use my programs in your research
work.

```
@article{Da04,
 author = {Ali Dasdan},
 title = {Experimental analysis of the fastest optimum cycle ratio and mean algorithms},
 journal = {ACM Transactions on Design Automation of Electronic Systems},
 volume = {9},
 number = {4},
 year = {2004},
 issn = {1084-4309},
 pages = {385--418},
 doi = {http://doi.acm.org/10.1145/1027084.1027085},
 publisher = {ACM Press},
 address = {New York, NY, USA},
 }
```
