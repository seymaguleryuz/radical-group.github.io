---
title: "Workflow Design Analysis for High Resolution Satellite Image Analysis"
collection: publications
permalink: /publications/paraskevakos2019workflow
date: 2019-05-24
type: pub
author: "Ioannis Paraskevakos, Matteo Turilli, Bento Collares Gonçalves, Heather J. Lynch and Shantenu Jha"
venue: "Arxiv"
paperurl: https://arxiv.org/abs/1905.09766
abstract: "Ecological sciences are using imagery from a variety of sources to 
monitor and survey populations and ecosystems. Very High Resolution (VHR) 
satellite imagery provide an effective dataset for large scale surveys. 
Convolutional Neural Networks have successfully been employed to analyze such 
imagery and detect large animals. As the datasets increase in volume, O(TB), 
and number of images, O(1k), utilizing High Performance Computing (HPC) 
resources becomes necessary. In this paper, we investigate a task-parallel 
data-driven workflows design to support imagery analysis pipelines with 
heterogeneous tasks on HPC. We analyze the capabilities of each design when 
processing a dataset of 3,000 VHR satellite images for a total of 4~TB. We 
experimentally model the execution time of the tasks of the image processing 
pipeline. We perform experiments to characterize the resource utilization, 
total time to completion, and overheads of each design. Based on the model, 
overhead and utilization analysis, we show which design approach to is best 
suited in scientific pipelines with similar characteristics."
---
