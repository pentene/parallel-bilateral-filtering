---
layout: page
title: "Parallel Bilateral Filtering Implementation and Optimization"
# permalink: /
---

<!-- ## Team Members
Zhaowei Zhang, Eric Zhu -->

# Project Website

[https://github.com/pentene/15418-final-project](https://github.com/pentene/15418-final-project)

---

## Summary

In this project, we will implement optimized parallel versions of the bilateral filtering algorithm on CPU and GPU platforms, specifically using **OpenMP** and **CUDA**, respectively. We aim to benchmark these implementations rigorously, analyzing their performance characteristics and scalability across diverse optimization strategies and hardware configurations.

---

## Background

Bilateral filtering is a widely-used image processing technique known for its effectiveness in smoothing images while preserving edges. This edge-preserving smoothing is accomplished
by calculating the filtered value for each pixel as a weighted average of neighboring pixels, considering both spatial proximity and intensity similarity.

The bilateral filter’s per-pixel computation involves intensive arithmetic operations and memory access, making it computationally expensive, particularly with large neighborhood
windows or high-resolution images. Each pixel’s computation involves accessing neighboring pixels within a defined radius repeatedly. Nonetheless, it exhibits good potential for par-
allelization since each pixel’s final output computation is independent of other pixels, even though there are neighborhood dependencies. Exploiting parallelism through CPU multi-
threading (OpenMP) and GPU massive threading (CUDA) can reduce execution time and enhance efficiency.

---

## Goals and Deliverables

Planned Goals:

- Achieve at least a 4x speedup with CPU parallelization using OpenMP compared to the sequential baseline.

- Achieve at least a 10x speedup with GPU parallelization using CUDA compared to the sequential baseline.

- Perform a thorough comparative analysis of performance and scalability between CPU and GPU implementations using image datasets such as High Resolution Image Quality (HRIQ) and The USC-SIPI Image Database.

- Validate correctness by comparing results with the OpenCV bilateral filtering implementation.

Aspirational Goals:

- Achieve a 10x speedup on CPU with robust scalability across varying image sizes.

- Achieve a speedup exceeding 50x on GPU through advanced optimizations such as FFT-based fast convolution techniques inspired by Sylvain Paris and Frédo Durand's work ("A Fast Approximation of the Bilateral Filter using a Signal Processing Approach").

Fallback Goals:

- Ensure fully functional parallel implementations with measured performance gains, even if the desired speedup targets are not fully met.

- Complete rigorous analysis clearly identifying bottlenecks and documenting performance insights.

---

## Challenges

Parallelizing bilateral filtering is challenging due to several critical factors:

- Workload dependencies: Pixel computations involve accessing neighboring pixels within a defined spatial radius. However, each pixel’s output calculation remains independent, allowing parallel computation.

- Memory access characteristics: Effective use of cache-aware techniques and shared memory optimizations is critical to exploit locality.

- Communication-to-Computation ratio: Frequent memory accesses can dominate execution without effective optimization. Using caching or shared memory significantly lowers this ratio.

- Divergent execution: Intensity-dependent calculations within the bilateral filter can lead to divergent execution patterns, particularly on GPUs.

- System constraints: GPU shared memory and CPU cache capacities heavily impact performance. Exceeding capacities necessitates frequent global memory accesses, degrading performance.

Through addressing these challenges, we aim to gain deep insights into optimizing memory access patterns, synchronization overhead, and computational efficiency in parallel systems.

---

## Resources

Implementation and benchmarking will be performed primarily on GHC lab machines and Pittsburgh Supercomputing Center (PSC) resources. Initial sequential implementations will be verified against OpenCV’s bilateral filter for correctness. 
PSC machines offer robust CPU and GPU capabilities for detailed performance profiling and large-scale experimentation.

Here is our current reference:

- Tomasi, C., & Manduchi, R. (1998). Bilateral filtering for gray and color images. Proceedings of the Sixth International Conference on Computer Vision, 839–846.

- Paris, S., & Durand, F. (2006). A fast approximation of the bilateral filter using a signal processing approach. European Conference on Computer Vision, 568–580.

- Paris, S., Kornprobst, P., Tumblin, J., & Durand, F. (2009). Bilateral filtering: Theory and applications. Foundations and Trends in Computer Graphics and Vision, 4(1), 1–73.

- [Nvidia documentation on bilateral filtering](https://docs.nvidia.com/vpi/algo_bilat_filter.html)

---

## Platform Choice

The GHC lab machines and PSC machines provide multi-core CPUs and GPU resources
suitable for our parallel implementations. GHC machines will facilitate development and
initial testing, while the powerful GPU systems at PSC will enable detailed performance
profiling and large-scale experimentation.

---

## Schedule (Tentative)

|   Week   | Planned Acrivity |
| -------- | ------- |
| 3.26 - 4.2  | Implement serial version of bilateral filter; begin OpenMP parallelization |
| 4.2 - 4.9   | Analyze CPU performance, identify bottlenecks, and optimize OpenMP parallelization using course techniques |
| 4.9 - 4.16  | Develop initial CUDA implementation; perform GPU profiling and identify bottlenecks |
| 4.16 - 4.23 | Optimize CUDA implementation based on analysis; evaluate GPU performance improvements |
| 4.23 - 4.28 | Finalize benchmarking results, prepare poster and presentation materials |
| 4.29        | Poster session |

