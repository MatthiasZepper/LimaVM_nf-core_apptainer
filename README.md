![nf-core header](docs/logoheader.svg)

# LimaVM: nf-core/apptainer

<p>
    <b>A virtual machine for Lima to run nf-core/Nextflow/Apptainer on a macOS host.</b>
</p>

<hr>

- [About](#about)
- [Installation](#installation-and-initial-start)
- [Usage](#usage)

<hr>

## About

Systems that are used for processing sensitive genomic information are typically restricted from freely accessing the internet for security concerns. This means that pipelines and their required dependencies need to be downloaded on a different computer and must subsequently be transferred. Ideally, both systems would share the same architecture and operating system, but in practice this is not guaranteed. For example, this virtual machine has been created to allow building containers for a Rocky Linux `x86_64` system while using a macOS `aarch64` laptop.

The virtual machine image in this repository can be run with [Lima](https://lima-vm.io/). It is primarily intended to be used on a macOS host, yet Lima also supports other container engines (Docker, Podman, Kubernetes, etc.) and non-macOS hosts (Linux, NetBSD, etc.).

In addition to the Ubuntu base image, this machine already comes with some additional software that is required to work with nf-core properly:

- [Apptainer](https://apptainer.org/docs/admin/main/index.html)
- [Nextflow](https://nextflow.io/docs/latest/index.html)
- [nf-core](https://pypi.org/project/nf-core/)

## Installation and initial start

To run this virtual machine, you need to install [Lima](https://lima-vm.io/) and [Qemu](https://www.qemu.org) first. Assuming you have installed [Homebrew](https://brew.sh/) on your macOS already, you can run

```shell
brew install qemu lima
```

to install both.

Subsequently, you can use the `nf-core_apptainer.yaml` from this repository to create a virtual machine. Since the architecture of a virtual machine can't be changed after instantiation, ensure that you are happy with the choice. By default, this image uses the `x86_64` architecture, but you can easily change it to `aarch64` if you like. Performance is significantly better if it matches your host architecture, but [Lima/Qemu can accommodate foreign architectures as well](https://lima-vm.io/docs/config/multi-arch/).

To build and start the virtual machine, run

```shell
limactl start nf-core_apptainer.yaml
```

The initial configuration and download of the dependencies will take several minutes to complete.

## Usage

After the machine has been instantiated, you can boot it with

```shell
limactl start nf-core_apptainer
```

To get shell access to the guest system, run

```shell
limactl shell nf-core_apptainer
```

To shutdown the machine, use

```shell
limactl stop nf-core_apptainer
```

In case you wish to delete the machine, you can type

```shell
limactl delete nf-core_apptainer
```

Please refer to the [nf-core documentation](https://nf-co.re/docs/nf-core-tools/) for the available commands and arguments.

## Customization

To customize the image, edit  `nf-core_apptainer.yaml` accordingly. [This example](https://github.com/lima-vm/lima/blob/master/examples/default.yaml) explains the available commands.
