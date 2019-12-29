# Sandbox Isolation

## Introduction

1. A [Sandboxes](https://en.wikipedia.org/wiki/Sandbox_(computer_security)) is a security mechanism for separating running programs, usually in an effort to mitigate system failures or software vulnerabilities from spreading.

---

## 1. Application built-in Sandboxes

1. `Chrome`, `Chromium`, `Firefox`, `Adobe Reader`, `Microsoft Apps`, implement `sandboxes`.

> NB: Not always reliable. Additional sandboxes can be added for `defence-in-depth`.

---

## 2. Windows Sandboxes

1. [Sandboxie](https://www.sandboxie.com/) - Install with `choco`.

2. [BufferZone](https://bufferzonesecurity.com/product/how-it-works), [DeepFreeze](https://www.faronics.com/en-uk/products/deep-freeze), others.

---

## 3. OSX Sandboxes

1. [sandbox, sandboxd, sandbox-init, sandbox-exec](https://www.howtogeek.com/344211/what-is-sandboxd-and-why-is-it-running-on-my-mac/)

    1. Works via `BSD Mandatory Access Controls`.

    2. Configured via a `config file` per `application` to be sandboxed.

---

## 4. Linux Sandboxes

1. __Linux Kernel Mandatory Access Control (MAC)__

    1. [AppArmor](https://gitlab.com/apparmor)
    
    2. [SELinux](https://github.com/SELinuxProject/selinux)
    
    3. [seccomp-bfp](https://www.kernel.org/doc/html/v4.16/userspace-api/seccomp_filter.html) etc.

2. [sandbox](https://linux.die.net/man/8/sandbox)

---

3. [firejail](https://firejail.wordpress.com/)

    1. `SELinux` + `seccomp-bpf`

---

## 5. BSD Sandboxes

1. [Trusted BSD](http://www.trustedbsd.org/)

