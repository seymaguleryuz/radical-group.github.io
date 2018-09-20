---
title: "Ensemble Toolkit: Scalable and Flexible Execution of Ensembles of Tasks"
collection: publications
permalink: /publications/entk-v1
type: pub
date: 2016-08-19
year: 2016
author: "Vivekanandan Balasubramanian, Antons Treikalis, Ole Weidner, and Shantenu Jha"
venue:  "45th International Conference on in Parallel Processing (ICPP), pp. 458-463. IEEE, 2016"
---

## Abstract:

There are many science applications that require scalable task-level parallelism
and support for flexible execution and coupling of ensembles of simulations. 
Most high-performance system software and middleware, however, are designed to 
support the execution and optimization of single tasks. Motivated by the missing
capabilities of these computing systems and the increasing importance of 
task-level parallelism, we introduce the Ensemble toolkit which has the 
following application development features: (i) abstractions that enable the 
expression of ensembles as primary entities, and (ii) support for ensemble-based 
execution patterns that capture the majority of application scenarios. Ensemble
toolkit uses a scalable pilot-based runtime system that decouples workload 
execution and resource management details from the expression of the 
application, and enables the efficient and dynamic execution of ensembles on 
heterogeneous computing resources. We investigate three execution patterns and 
characterize the scalability and overhead of Ensemble toolkit for these 
patterns. We investigate scaling properties for up to O(1000) concurrent 
ensembles and O(1000) cores and find linear weak and strong scaling behavior. 

[Paper URL](http://ieeexplore.ieee.org/abstract/document/7573848/)
