---
title: "Characterizing the Performance of Executing Many-tasks on Summit"
collection: publications
permalink: /publications/turilli2019characterizing
type: pub
date: 2019-09-08
author: "Matteo Turilli, Andre Merzky, Thomas J. Naughton, Wael Elwasif, Shantenu Jha"
venue: IPDRM 2019, Held in conjunction with the International Conference for High Performance Computing, Networking, Storage and Analysis, (SC 19), November 17-22, 2019, Denver, Colorado, USA.
paperurl: https://arxiv.org/abs/1909.03057
abstract: "Many scientific workloads are comprised of many tasks, where each task is an independent simulation or analysis of data. The execution of millions of tasks on heterogeneous HPC platforms requires scalable dynamic resource management and multi-level scheduling. RADICAL-Pilot (RP) -- an implementation of the Pilot abstraction, addresses these challenges and serves as an effective runtime system to execute workloads comprised of many tasks. In this paper, we characterize the performance of executing many tasks using RP when interfaced with JSM and PRRTE on Summit: RP is responsible for resource management and task scheduling on acquired resource; JSM or PRRTE enact the placement of launching of scheduled tasks. Our experiments provide lower bounds on the performance of RP when integrated with JSM and PRRTE. Specifically, for workloads comprised of homogeneous single-core, 15 minutes-long tasks we find that: PRRTE scales better than JSM for > O(1000) tasks; PRRTE overheads are negligible; and PRRTE supports optimizations that lower the impact of overheads and enable resource utilization of 63% when executing O(16K), 1-core tasks over 404 compute nodes."
---
