---
title: "Risotto: A Dynamic Binary Translator for Weak Memory Model Architectures"
date: 2023-01-01
venueType: "Conference"
venue: "In proceedings of the 28th ACM International Conference on Architectural Support for Programming Languages and Operating Systems"
author: ["Redha Gouicem", "Dennis Sprokholt", "Jasper Ruehl", "Rodrigo C. O. Rocha", "Tom Spink", "Soham Chakraborty", "Pramod Bhatotia"]
tags: []
draft: false
---

Dynamic Binary Translation (DBT) is a powerful approach to support cross-architecture emulation of unmodified binaries.  However, DBT systems face correctness and performance challenges, when emulating concurrent binaries from strong to weak memory consistency architectures.  As a matter of fact, we report several translation errors in Qemu, when emulating x86 binaries on Arm hosts.

To address these challenges, we propose an end-to-end approach that provides correct and efficient emulation for weak memory model architectures.  Our contributions are twofold: First, we formalize Qemu's intermediate representation's memory model, and use it to propose formally verified mapping schemes to bridge the strong-on-weak memory consistency mismatch.  Second, we implement these verified mappings in Risotto, a Qemu-based DBT system that optimizes memory fence placement while ensuring correctness.  Risotto further improves performance via cross-architecture dynamic linking of native shared libraries and faster yet correct translation of compare-and-swap operations.

We evaluate Risotto using multi-threaded benchmark suites and real-world applications, and show that Risotto improves the emulation performance by 6.7% on average over "erroneous" Qemu, while ensuring correctness.
