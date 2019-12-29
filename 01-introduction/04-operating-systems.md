# Operating Systems

## Introduction

1. `Operating Systems` are the first line of defence against attackers.

2. `Operating Systems` have different `functionality`, `security`, and, `anonymity` trade-offs.

    1. Some `functionality` and `security` may be at the cost of `anonymity`.

3. The best defensive measure is to ensure an `OS` is regularly safely `updated` and `patched`.

---

## Windows 7/8

> __Strong__ for `usability`.

> __Moderate__ for `security` if regularly `updated`, `endpoint protection` enabled, and, `firewalls` configured correctly. Third-party software available.

> __Moderate__ for `privacy` due to closed source nature. `Bitlocker encryption` is closed source.

> __Moderate__ for `anonymity` due to `tracking`, and `phone home` issues. Do not use `TOR`. Anonymity nightmare?

1. High market share. High attack profile.

---

## Windows 10

> __Strong__ for `usability`.

> __Moderate__ for `security` if regularly `updated`, `endpoint protection` enabled, and, `firewalls` configured correctly. Third-party software available.

> __Weak__ for `privacy` due to closed source nature. `Bitlocker encryption` is closed source.

> __Weak__ for `anonymity` due to `tracking`, and `phone home` issues. Do not use `TOR`. Anonymity nightmare?


1. High market share. High attack profile.

2. `Security` concerns unless patched and additional `security controls` enabled.

    1. Has some built in tools under `Settings` --> `Update and Security`.

2. Serious `anonymity` and `tracking` concerns unless tacking features are disabled. __Disable Windows Tracking__.

    1. Does lots of tracking and data gathering. Especialy when `Cortana`, `Phone`, and, `mike/webcam` are enabled.

    2. These can be disabled under `Settings` --> `Privacy`, `Cortana`, etc.

3. Has built in `security` and `privacy`.

    1. `Windows Defender` - Anti-virus.

    2. `Windows Firewall` - Firewall.

    3. `Bitlocker` - Disk encryption and firmware modification detection.

        1. Window Pro only.

        2. Requires 2 partitions and `Trusted Platform Module (TPM)` hardware module. 

        3. Closed source. Backdoors? TrueCrypt? Trust?
    
    4. `Device Guard` - Used to check `Digital Signatures` of `drivers` and `software` and prevent them being executed if cannot be proved to be valid.

4. __Settings__

    1. __Privacy Settings__ - Disable/Enabled `tracking` features as applicable.

    2. __Cortana__ - Disable/Enabled `tracking` features as applicable.

    3. __Update and Security__ - Configure `Updates`, `Anti-virus`, `Backup`, `Recovery` as applicable.

    4. __Network and Internet__ - Configure `Firewall`, and 

---

## Mac OSX

> __Strong__ for `usability`.

> __Moderate__ for `security` if regularly `updated`, and, `firewalls` configured correctly.

> __Strong__ for `privacy` IFF you __trust__ Apple. Closed source nature.

> __Moderate__ for `anonymity` due to `tracking`, and `phone home` issues. Do not use `TOR`.

1. Average attack profile.

2. Strong for `security`. Weak for `privacy`.

3. Suitable for general use. Trades off security for usability.

    1. BSD Unix based.

    2. Apple claim to protect data.

    3. Curated `App store`.

4. Has `privacy concerns`. Application may have `callbacks` / `phone home` to Apple.

    1. `spotlight` send `user` and `location` data when performing a search. This can be disabled in `Preferences`.

    2. Configure `Location services` as applicable.

---

## General Usage Linux - Ubuntu / Mint / Manjaro

> __Moderate__ for `usability`.

> __Strong__ for `security` if regularly `updated`, and, `firewalls` configured correctly.

> __Strong__ for `privacy`. Open source nature.

> __Strong__ for `anonymity` - provided web browser are hardened.

1. Low attack profile.

2. Suitable for general use. Trades off security for usability.

    1. Linux based. Open source.

    2. Cutting edge kernel and packages.

3. Unix user privilege system, firewalls, kernel hardening.

---

## Security Focused Linux - Debian / Redhat / CentOS / Arch / Oracle Linux

> __Weak__ for `usability`.

> __Strong__ for `security` if regularly `updated`, and, `firewalls` configured correctly.

> __Strong__ for `privacy`. Open source nature.

> __Strong__ for `anonymity` - provided web browser are hardened.

1. Low attack profile.

2. `Security` focus.

3. Suitable for advanced use. Stronger focus on security and stability.

    1. Linux based. Open source.

    2. Stable kernel and packages.

4. Unix user privilege system, firewalls, kernel hardening.

---

## BSD - Open BSD

> __Weak__ for `usability`.

> __Strong__ for `security` if regularly `updated`, and, `firewalls` configured correctly.

> __Strong__ for `privacy`. Open source nature.

> __Strong__ for `anonymity` - provided web browser are hardened.

1. Low attack profile.

2. Suitable for advanced use. Stronger focus on security and stability.

    1. Linux based. Open source.

    2. Stable kernel and packages.

3. Unix user privilege system, firewalls, kernel hardening.

---

## Qubes OS

1. `Pure Security` focused.

2. `Virtualization` and `Compartmentalisation` based operating system.

---

## Subgraph OS

1. `Pure Security` focused.

2. __Features__

    1. `Endpoint protection` based operating system.

    2. `Security hardening`.

    3. `Sandboxed` processes.

    4. `TOR default` routing. Anonymised.

---

## Tails OS

1. `Pure Anonymity` focused.

2. __Features__

    1. Resistant to local forensic analysis - `USB driven`.

    2. Reproducible builds.

---

## Whonix OS

1. `Pure Anonymity` focused.

2. __Features__

    1. Comprises of two parts: 

        1. `Gateway` - Server.

        2. `Host` - Client.

    2. `TOR` anonymity network.

    3. `Security through isolation`. Integration with `Qubes OS`.

---

## Kali Linux

1. `Penetration Testing` focused.

