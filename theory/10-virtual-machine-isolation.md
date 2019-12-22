# Virtual Machine

## Introduction

1. A [virtual machine](https://en.wikipedia.org/wiki/Virtual_machine) - An emulation of a computer system running on a `host`.

2. A `virtual machine` adds `isolation` and `compartmentalisation` security controls.

    1. __Isolation__ - A `virtual machine` is unaware that it is virtual and running on a `host`.

    2. __Compartmentalisation__ - If a `virtual machine` is compromised; hopefully the the attack cannot escape out to the `host`.

---

## Type 1 - Native (Bare Metal)

1. The `hypervisor` runs _directly on the hardware_ as the main OS.

2. `[hardware] ---> [hypervisor] ---> [os1, os2,...,osN]`

3. `KVM`, `XenServer`, `Oracle VM server`, `VMware ESX/ESXi`, `Microsoft Hyper V`, etc.

    1. [Xen Project](https://xenproject.org).

    2. [Xen Server](https://xenserver.org).

    3. [xcp-ng](https://xcp-ng.org).

4. Generally faster and more secure than `Type 2`.

---

## Type 2 - Hosted

1. The `hypervisor` runs _on top of the main OS_.

2. `[Hardware] ---> [os] ---> [hypervisor1 ---> [os11, os12, ... , os1N] , hypervisorN] ---> [osN1, osN2, ... , osNN]]`

3. `KVM`, `Virtual Box`, `VMWare Player/Fusion/Workstations`, etc.

---

## Hybrid

1. Convert a capable `operating system` to a `Type 1` Hypervisor. 

2. `Linux / KVM`.

