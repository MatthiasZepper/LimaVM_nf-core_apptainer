![nf-core header](docs/logoheader.svg)

# LimaVM: nf-core/apptainer

<p>
    <b>A virtual machine for Lima to run nf-core/Nextflow/Apptainer on a macOS host.</b>
</p>

<hr>

- [About](#about)
- [Installation](#installation)
- [Usage](#usage)

<hr>

## About

Systems that are used for processing sensitive genomic information are typically restricted from freely accessing the internet for security. This means that pipelines and their required dependencies need to be downloaded on a different computer and must subsequently be transferred. Ideally, both systems would share the same architecture and operating system, but in practice this is not guaranteed. For example, this virtual machine has been created to allow building containers for a Rocky Linux `x86_64` system while using a macOS `aarch64` laptop.

The virtual machine image in this repository can be run with [Lima](https://lima-vm.io/). It is primarily intended to be used on a macOS host, yet Lima also supports other container engines (Docker, Podman, Kubernetes, etc.) and non-macOS hosts (Linux, NetBSD, etc.).

In addition to the Ubuntu base image, this machine already comes with some additional software that is required to work with nf-core properly:

- [Apptainer](https://apptainer.org/docs/admin/main/index.html)
- [Nextflow](https://nextflow.io/docs/latest/index.html)
- [nf-core](https://pypi.org/project/nf-core/)

## Installation

## Usage