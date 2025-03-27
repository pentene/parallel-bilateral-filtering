---
layout: page
title: "Parallel Bilateral Filtering Implementation and Optimization"
# permalink: /
---

## Team Members
Zhaowei Zhang, Eric Zhu

## URL
[[text](https://github.com/pentene/15418-final-project)]

## Summary
In this project, we will implement optimized parallel versions of the bilateral filtering algorithm on CPU and GPU platforms, specifically using OpenMP and CUDA, respectively.
We aim to benchmark these implementations rigorously, analyzing their performance characteristics and scalability across diverse optimization strategies and hardware configurations.

## Background
Bilateral filtering is a widely-used image processing technique known for its effectiveness in smoothing images while preserving edges.This edge-preserving smoothing is accomplished
by calculating the filtered value for each pixel as a weighted average of neighboring pixels, considering both spatial proximity and intensity similarity. 

## The Challenge
The challenge lies in effectively parallelizing and optimizing memory access patterns, given bilateral filtering's inherent data-intensive nature. The algorithm requires intensive data access within each pixel's neighborhood, leading to challenges in memory bandwidth and cache performance on CPUs, and shared memory optimization and memory coalescing on GPUs. Ensuring minimal synchronization and efficient data-sharing among threads further complicates parallel implementation.

## Resources
We will use standard lab machines with multi-core CPUs and CUDA-capable GPUs. The project starts from scratch, developing implementations using OpenMP for CPU parallelization and CUDA for GPU acceleration. Essential references include:
- C. Tomasi and R. Manduchi, "Bilateral Filtering for Gray and Color Images," ICCV, 1998.
- NVIDIA CUDA Programming Guide

## Goals and Deliverables
### Plan to Achieve:
- Sequential bilateral filtering baseline implementation.
- Parallel bilateral filtering with OpenMP, achieving measurable speedup (targeting ~4-8x on 8-core CPU).
- GPU implementation using CUDA with basic optimizations (targeting at least 10-20x improvement over sequential).
- Detailed benchmarking and comparative performance analysis between CPU and GPU versions.

### Hope to Achieve (if time permits):
- Advanced GPU optimizations (shared memory, coalescing), targeting additional 2-4x speedup.
- Analysis of scalability on higher-resolution images.

## Platform Choice
CPU with OpenMP allows effective parallelization and rapid prototyping of image processing kernels, whereas GPUs using CUDA provide substantial parallel arithmetic capability ideal for computationally heavy bilateral filtering. The combination enables insightful comparative analysis.

## Schedule (Tentative)
