---
title: "Task-parallel Analysis of Molecular Dynamics Trajectories"
collection: publications
permalink: /publications/task-parallel-analysis
date: 2018-08-15
type: pub
author: "Ioannis Paraskevakos, Andre Luckow, Mahzad Khoshlessan, George Chantzialexiou, Thomas E. Cheatham, Oliver Beckstein, Geoffrey C. Fox and Shantenu Jha"
venue: "47th International Conference on Parallel Processing (ICPP 2018)"
---

## Abstract:
Different parallel frameworks for implementing data analysis applications have 
been proposed by the HPC and Big Data communities. In this paper, we investigate 
three task-parallel frameworks: Spark, Dask and RADICAL-Pilot with respect to 
their ability to support data analytics on HPC resources and compare them with 
MPI. We investigate the data analysis requirements of Molecular Dynamics (MD) 
simulations which are significant consumers of supercomputing cycles, producing 
immense amounts of data. A typical large-scale MD simulation of a physical system 
of O(100k) atoms over {\mu}secs can produce from O(10) GB to O(1000) GBs of data. 
We propose and evaluate different approaches for parallelization of a representative 
set of MD trajectory analysis algorithms, in particular the computation of path 
similarity and leaflet identification. We evaluate Spark, Dask and RADICAL-Pilot 
with respect to their abstractions and runtime engine capabilities to support 
these algorithms. We provide a conceptual basis for comparing and understanding 
different frameworks that enable users to select the optimal system for each 
application. We also provide a quantitative performance analysis of the different 
algorithms across the three frameworks.



[Paper URL](https://dl.acm.org/citation.cfm?id=3225128)

