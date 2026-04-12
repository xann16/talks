## Always Measure: Analyzing Performance of Point-Particle DNS under Two-Way Momentum Coupling

Language: English.

**Co-authors**: Bogdan ROSA, Ahmad ABABAEI.

**Abstract**:

Computational efficiency matters a lot for scientific software, whether it allows to save valuable CPU-hours on HPC systems, to complete weather predictions within strict operational time windows, or simply to enable moderately complex research codes to run on personal laptops. Although we often rely on intuition to predict whether code will be fast or slow, such intuition is increasingly unreliable. Multiple layers separate the code we write from the instructions executed on modern hardware, and these layers are both complex and opaque. The intricacies of modern CPU architectures and the sophisticated transformations applied by optimizing compilers, among other factors, make it difficult to reason about performance a priori. Consequently, in communities where performance matters, one guiding principle is widely embraced: “Always measure.”

This presentation first introduces fundamental performance assessment techniques—such as benchmarking and profiling—highlighting both their value and their common pitfalls. Several illustrative examples are presented where measurements contradict intuitive expectations. More importantly, we report a detailed performance analysis of a well-established direct numerical simulation (DNS) code used to study the influence of atmospheric turbulence on cloud droplet behavior. The software comprises two tightly coupled components: a pseudo-spectral fluid solver operating on an Eulerian regular box grid with periodic boundary conditions, and a Lagrangian module tracking individual point particles (droplets) that interact with the carrier flow. The code is optimized for massively parallel execution by employing a two-dimensional domain decomposition (into “pencils” or “columns”) to enable efficient three- dimensional Fast Fourier Transforms.

The results of execution time measurements, collected using minimally intrusive manual instrumentation, are presented in various scenarios. The resulting data reveal notable discrepancies from an earlier performance study of the same code, primarily due to the use of substantially larger particle counts (to model regime where two-way momentum coupling is relevant). These discrepancies prompted a deeper investigation into how particle distribution across subdomains affects performance. Earlier assumptions of near-homogeneous particle distributions at this scale proved invalid, particularly when gravity introduces anisotropy in the system. In practical terms, this insight led to a simple two-line modification that, counterintuitively, orients gravity perpendicular to the subdomain “pencils.” This change was shown to speed up simulations by up to 30%.

These findings underscore the necessity of measuring software performance and revisiting prior assumptions whenever numerical methods or physical parameters evolve. They also highlight additional challenges, more specific to research software, that further complicate performance reasoning, including distributed computation and the influence of physical parameters on the modeled system. Therefore, the imperative to “Always measure” is paramount to the development and use of scientific software. 


Delivered on 08.04.2026 during conference *Improving Scientific Software 2026* organized by UCAR Software Engineering Assembly in Boulder, CO, USA (remote presentation, video recording might be available later).
