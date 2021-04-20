---
title: System Overview
date: 2018-01-01
url: /overview
---

Isambard is a HPC service provided by [GW4](http://gw4.ac.uk/) and the [UK Met Office](https://www.metoffice.gov.uk/). The system is funded by [EPSRC](http://www.epsrc.ac.uk/) and is one of a number of [Tier-2 HPC facilities](http://www.hpc-uk.ac.uk/facilities/) in the UK.

Isambard includes a production Cray XC50 system, named "XCI", which comprises 20,992 cores, and is one of the world’s first production Arm-based supercomputers. While Isambard is not based on the more common x86 processors from Intel and AMD, most software compiles and runs on Isambard with no or minimal changes.

Each of the 329 compute nodes contain two 32-core Marvell ThunderX2 processors running at 2.5 GHz. 160 nodes have 256 GB and 169 have 512 GB of memory, both at DDR4-2666MHz. The nodes are connected via Cray Aries interconnect in a Dragonfly topology. A Cray Sonexion 3000 storage cabinet provides 900 terabytes of Lustre storage.

Isambard includes one of the first production Fujitsu A64FX CPU clusters, which comprises 72 nodes of 1.8GHz ARMv8.2 CPUs with scalable vector extension (SVE) up to 512-bit, 32GB HBM2 memory on the die arranged in 4 Core Memory Groups (CMGs) each with 12 cores, 8GB HBM2, 64KB private L1 cache & 8MB shared L2 cache per CMG. 

A64FX is connected with EDR InfiniBand and has access to a dedicated 660GB Lustre filesystem alongside the existing Lustre filesystem.

The Isambard service also includes the Multi-Architecture Comparison System, or "MACS", which comprises a Cray CS cabinet with a diverse set of nodes:

- 2x Login nodes with [Intel Xeon “Broadwell”](https://ark.intel.com/content/www/us/en/ark/products/91316/intel-xeon-processor-e5-2695-v4-45m-cache-2-10-ghz.html) CPU
- 4x nodes of Nvidia Pascal GPU with 2x [Nvidia P100 “Pascal”](https://www.nvidia.com/en-us/data-center/pascal-gpu-architecture/) GPUs and Intel Xeon E5-2695 v4 “Broadwell” CPU
- 4x nodes of Nvidia Volta GPU with 1x [Nvidia V100 “Volta”](https://www.nvidia.com/en-us/data-center/volta-gpu-architecture/) GPU and Intel Xeon Gold 6230 “Cascade Lake (CLX)” CPU
- 4x nodes of [AMD Epyc 7742 “Rome”](https://www.amd.com/en/products/cpu/amd-epyc-7742) @ 2.25GHz 64-core CPU nodes with DDR4-3200Mhz over 8 memory channels, AVX-512
- 4x nodes of [Intel Xeon Gold 6230 “Cascade Lake (CLX)”](https://ark.intel.com/content/www/us/en/ark/products/192437/intel-xeon-gold-6230-processor-27-5m-cache-2-10-ghz.html) @ 2.10GHz 20-core CPU nodes with DDR4-2933MHz over 6 memory channels, AVX-512
- 8x nodes of [Intel Xeon Phi “Knights Landing” 7210 CPU](https://ark.intel.com/products/94033/Intel-Xeon-Phi-Processor-7210-16GB-1_30-GHz-64-core) @ 1.30GHz (1.50GHz Turbo) with AVX-512; 4x nodes set HBM2 in cache mode & 4x nodes set HBM2 as extended memory
- 2x nodes of [IBM Power 9 System AC922](https://www.ibm.com/uk-en/marketplace/power-systems-ac922) with 2x Nvidia V100 “Volta” GPU

## Evolving system

MACS has gone through several revisions, including upgrading the base operating system up through the RHEL 7.x series. Now with the upgrade to RHEL 8 we can take lessons learned and improve our software deployment processes. MACS has been augmented with more interesting architectures over time, expanding on our GPU nodes with newer Volta nodes and adding to the x86 pool with Intel Cascade Lake CPU nodes.

Isambard operated some of the first ThunderX2 Arm compute nodes through collaboration with Cavium, this provided us a glimpse into the platform's performance characteristics. The Linux kernel was patched by Cray to include upstream patches from Cavium to better support ThunderX2. Initially the CPU hardware revision we were provided only worked in single-socket mode, firmware updates were applied through hardware-flashing the ROM chips and new ThunderX2 hardware revisions were supplied to enable dual-socket operation. These nodes were retired once XCI was running in production.

Intel loaned Isambard two Skylake nodes, these were used to compare Skylake against Broadwell CPU performance, and to compare Thunder X2 against Intel's current HPC platform. These were also the first Intel CPUs to support AVX-512 since its introduction in the Knights Landing many-core CPU series. These nodes have been retired.

IBM Power 9 AC922 nodes were added to complete our coverage of the current CPU ecosystem, each node has two Nvidia Volta GPUs connected via IBM's CAPI bus. Summit, the world's #1 supercomputer as of 2020, uses these nodes.

XCI was expanded in November 2018, doubling its CPU capacity with high memory nodes. These integrate seamlessly into the existing service, connecting to the same Aries interconnect electrical group, which ensures equivilent per-node performance characteristics across the cluster.

A64FX was installed late 2020, the cluster is equipped with Fujitsu A64FX CPUs designed for Fugaku, the world's #1 supercomputer as of early 2021, which include HBM2 memory integrated directory on the die and the world's first implementation of Arm Scalable Vector Extensions. Isambard's A64FX is unique for supporting the full Cray software stack & compilers.