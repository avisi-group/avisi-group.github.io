---
title: "Leaps and bounds: Analysing WebAssembly’s performance with a focus on bounds checking"
date: 2022-11-08
venueType: "Conference"
venue: "In Proceedings of the 2022 IEEE International Symposium on Workload Characterization"
author: ["Raven Szewczyk", "Kim Stonehouse", "Antonio Barbalace", "Tom Spink"]
doi: "https://doi.org/10.475/1234.5678"
tags: []
---

WebAssembly is gaining more and more popularity, finding applications beyond the Web browser -- for which it was initially designed for. However, its performance, which developers aimed at being comparable to native, requires further tuning and hasn't being studied extensively to pinpoint the cause of overheads. This paper identifies that WebAssembly unique safety mechanisms, one of the major ones being bounds-checked memory accesses, may introduce up to 650% overhead.

Therefore, we evaluate four popular WebAssembly runtimes against native compiled code. These runtimes have been enriched with modern bounds checking mechanisms and run on three different ISA CPUs, including x86-64, Armv8 and RISC-V RV64GC. We show that performance-oriented runtimes are able to achieve performance within 20% of the native performance on x86_64 platforms, 35% for Armv8. On RISC-V the V8 runtime can achieve a 17% overhead over native code for simple numeric kernels. For simple numerical kernels, we have shown that there is no significant difference in the WebAssembly performance compared to native code across different ISAs.

We have shown that in case of multithreaded scaling of the tested runtimes, which might for example be used to quickly scale up serverless instances for a single function without the overhead of spawning new processes, the default approach taken by WAVM, Wasmtime and V8 of using the mprotect syscall to resize memory can cause excessive locking in the Linux kernel and present an alternative userfaultfd-based solution to mitigate this issue.

We share our results and the tools and scripts under an open source license for other researchers to replicate our results, and monitor the progress that WebAssembly runtimes make as this technology evolves.
