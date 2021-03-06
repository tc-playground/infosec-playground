# Security Domains

## Introduction

1. `Security domains` handle different security requirements `availability`, `security`, `privacy`, `anonymity` , and are often __conflicting__.

    * There are often `trade-offs` that are impossible to accomplish in `a single environment` e.g. Gaming vs Full-disk Encryption.

2. Security can split over several `security domain` with each one tailored to the required security needs.

    * Run dual boot laptop without full disk-encryption; run VMs with full-disk encryption inside for secure operations.

3. `Security domain`s can be either:

    1. `Physical` - e.g. Have a separate machines for tasks A and B.

    2. `Virtual (Isolation)` - e.g. User VMs or containers for tasks A and B.

4. `Isolation and Compartmentalisation` is used to implement different `security domains`.

> `MAC Addresses` are __unique__ so must be changed if _anonymity_ is important and there is a trace to the purchase of the card.

---

## Physical Security Domain Mechanisms

1. __Multiple Machines__

2. __Encrypted USB Keys__

3. __USB Wireless Adaptors__

4. __Yubi Keys__

---

## Virtual Security Domain Mechanisms

1. __Dual Boot__

2. __Sandboxing__

3. __Containerised Applications__

4. __Virtual Machines__

5. __Container based security operating systems__

6. __USB privacy based operating systems__

7. __Cloud provisioned machines__

