---
layout: page
title: "Parallel Bilateral Filtering Implementation and Optimization"
# permalink: /
---

<!-- ## Team Members
Zhaowei Zhang, Eric Zhu -->

# Project Website

[https://pentene.github.io/parallel-bilateral-filtering](https://pentene.github.io/parallel-bilateral-filtering)

---

## Summary

In this project, we will implement optimized parallel versions of the bilateral filtering algorithm on CPU and GPU platforms, specifically using **OpenMP** and **CUDA**, respectively. We aim to benchmark these implementations rigorously, analyzing their performance characteristics and scalability across diverse optimization strategies and hardware configurations.

---

## Background

Bilateral filtering is a widely-used image processing technique known for its effectiveness in smoothing images while preserving edges. This edge-preserving smoothing is accomplished
by calculating the filtered value for each pixel as a weighted average of neighboring pixels, considering both spatial proximity and intensity similarity.

## Goals and Deliverables

### Planned Goals

- Achieve at least a 4x speedup with CPU parallelization using OpenMP compared to the sequential baseline.

- Achieve at least a 10x speedup with GPU parallelization using CUDA compared to the sequential baseline.

- Perform a thorough comparative analysis of performance and scalability between CPU and GPU implementations using image datasets such as High Resolution Image Quality (HRIQ) and The USC-SIPI Image Database.

- Validate correctness by comparing results with the OpenCV bilateral filtering implementation.

### Aspirational Goals

- Achieve a 10x speedup on CPU with robust scalability across varying image sizes.

- Achieve a speedup exceeding 50x on GPU through advanced optimizations such as FFT-based fast convolution techniques inspired by Sylvain Paris and Frédo Durand's work ("A Fast Approximation of the Bilateral Filter using a Signal Processing Approach").

### Fallback Goals

- Ensure fully functional parallel implementations with measured performance gains, even if the desired speedup targets are not fully met.

- Complete rigorous analysis clearly identifying bottlenecks and documenting performance insights.



## Schedule (Tentative)

