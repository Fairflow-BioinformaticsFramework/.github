# FairFlow: A Transparency-First Framework for Verifiable and Reproducible Bioinformatics

Welcome to the **Fairflow-BioinformaticsFramework** organization. We provide a suite of tools and a framework designed to make bioinformatics analyses verifiable, reproducible, and transparent by construction.

> **Our Mission**: To turn bioinformatics scripts into auditable, ready-to-run pipelines by combining immutable containerization with a declarative interface specification.

##  About FairFlow

Computational reproducibility is often compromised by hidden dependencies and environment drift. **FairFlow** addresses this by decoupling the **pipeline logic** from the **execution environment**.

Our approach relies on two pillars:
1.  **Immutable Containers**: Environments built with **CREDO** that are fully pinned and time-stable.
2.  **Declarative Interfaces**: Defined in **Baryon (Baryon Language)**, specifying generic inputs/outputs that can be transpiled into any frontend (R, Python, Bash, Galaxy).

This ensures that your analysis yields identical outputs across different operating systems (Linux, macOS, Windows) and hardware architectures.

## Repository Guide

Here is an overview of the repositories in this organization and their roles in the framework.

### Learning & Documentation
*   [**Tutorial_Fairflow**](https://github.com/Fairflow-BioinformaticsFramework/Tutorial_Fairflow): **Start Here!** The canonical guide to the FairFlow path. It covers everything from building containers to writing `.bala` files.
*   [**Tutorial_CARNGS**](https://github.com/Fairflow-BioinformaticsFramework/Tutorial_CARNGS): Specific tutorials for the CAR-NGS suite of pipelines.

### Core Framework Tools
*   [**baryon-lang**](https://github.com/Fairflow-BioinformaticsFramework/baryon-lang): The **Baryon Language Compiler**. This tool reads `.bala` specification files and generates user-friendly wrappers for R, Python, Bash, and Galaxy.
*   [**DockerBuilder**](https://github.com/Fairflow-BioinformaticsFramework/DockerBuilder): Helper scripts and templates for building **reproducible Docker images** using CREDO. Safeguards against "dependency drift".
*   [**baryon**](https://github.com/Fairflow-BioinformaticsFramework/baryon): Core definitions and examples for the Baryon project.

### Galaxy Integration
FairFlow makes it easy to bring your tools into Galaxy without complex configuration.
*   [**galaxy-formed**](https://github.com/Fairflow-BioinformaticsFramework/galaxy-formed): An immutable, Dockerized **Galaxy distribution** pre-configured to work with Baryon.
*   [**lemaitre**](https://github.com/Fairflow-BioinformaticsFramework/lemaitre): A lightweight service for **drag-and-drop tool installation** into Galaxy. Upload your generated wrapper, and it appears in Galaxy instantly.
*   [**galaxy-formation**](https://github.com/Fairflow-BioinformaticsFramework/galaxy-formation): Ansible playbooks for setting up the Galaxy environment.
*   [**docker-galaxy**](https://github.com/Fairflow-BioinformaticsFramework/docker-galaxy): Infrastructure for the Galaxy container.

### Example Pipelines (CAR-NGS)
**CAR-NGS** is our flagship suite of NGS pipelines (16S, RNA-seq, ATAC-seq, etc.) built entirely with FairFlow.
*   [**CAR-NGS**](https://github.com/Fairflow-BioinformaticsFramework/CAR-NGS): The **Frontend**. Contains the auto-generated R functions that users install to run analyses.
*   [**CAR-NGS_Backend**](https://github.com/Fairflow-BioinformaticsFramework/CAR-NGS_Backend): The **Backend**. Contains the Docker build contexts (scripts, Dockerfiles) for the pipelines.

### Helper Libraries
*   [**rrundocker**](https://github.com/Fairflow-BioinformaticsFramework/rrundocker): R utility for managing Docker execution.
*   [**normalizepath**](https://github.com/Fairflow-BioinformaticsFramework/normalizepath): Path handling utility ensuring cross-platform compatibility (Windows/POSIX).
*   [**withscratch**](https://github.com/Fairflow-BioinformaticsFramework/withscratch): Helper for managing scratch/temporary directories in analysis workflows.

---

## Getting Started

1.  **Read the Paper**: *FairFlow: A Transparency-First Framework for Verifiable and Reproducible Bioinformatics*.
2.  **Follow the Tutorial**: Go to [**Tutorial_Fairflow**](https://github.com/Fairflow-BioinformaticsFramework/Tutorial_Fairflow) to build your first reproducible pipeline.
3.  **Use an Existing Pipeline**: Install [**CAR-NGS**](https://github.com/Fairflow-BioinformaticsFramework/CAR-NGS) in R to run verified NGS workflows.

```r
# Example: Installing CAR-NGS
library(devtools)
install_github("https://github.com/Fairflow-BioinformaticsFramework/CAR-NGS", ref="main")
```

---
*Maintained by the FairFlow Team.*
