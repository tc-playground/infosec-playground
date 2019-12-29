# Privilege

## Introduction

1. `Privileges` denoted what a `principal` (user, service, processes, etc.) can and cannot do.

2. Most operating systems have a user level of `root` that permits everything.

3. `Users`, should only be given _the minimum_ required `privileges`.

---

## Linux - Principals and Resources

1. Linux has the concept of a `resource`. 

    1. All `resources` are some special kind of `file`.

    2. All `resources` have `read`, `write`, and `execute` capabilities set on them:

        NB:  They also have some additional extended properties - `Access Control Lists (ACLs)`

    2. All `resources` can be assigned metadata denoting what `operations` `user`, `group`, and `other` .

2. Linux has the concept of `users` - Denoted by an integer `UID` and entry in the password file.

    1.  The `root` user. Often this can be disabled and the `sudo` program used instead.

    2. Privileges on a `resource` can be defined based on `user`.

3. Linux has the concept of `groups`. 

    1. A `user` can be associated with multiple `groups`.

    2. Privileges on a `resource` can be defined based on `user`.

4. Linux has the concept of `other`.

    1. Privileges on a `resource` for principals that do not belong to the associated `user` or `group` can be defined based on `other`. 

---

## Linux - Access Control Lists

1. Linux has `Access Control List` functionality to extend the basic primitives.

---

## Linux - Mandatory Access Control

1. The Linux Kernel can use `kernel modules` to `harden` the kernel by defining stricter controls on what `system calls` a `process` can perform.

---

## Linux Kernel Capabilities

1. The `linux kernel` can be compiled with different `capabilities` to control what operations the kernel can perform.

---

## Windows

1. Don't runs as `Administrator`. Create an additional normal user account.