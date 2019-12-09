# The Threat Landscape

## The need for Security

1. Many attacks are not targeted; they are automated with a wide-cast by botnets and automated tools.

2. All digital resources (servers, accounts, identities, etc) are valuable; either in themselves or as a step towards some other resource.

3. `Complexity` is the enemy of `Security`.

---

## Vulnerabilities

1. There are two main classes of `vulnerability`:

   1. `Known` - Already discovered and reported

      1. Known Vulnerabilities are assigned `CVE number`.

         - - [Exploit DB](https://www.exploit-db.com/) - A database of known exploits.

      2. Known vulnerabilities often already have a `patch` to resolve the vulnerability.

      3. Know vulnerabilities are often used by hacking frameworks such a `Metasploit`.

   2. `Unknown` - `Zero Day Vulnerabilities`. These are often available for sale on the `dark web`.

---

## `Hackers` / `Cyber Criminals`

1. Individuals or groups attempting to compromise resources with various motives.

---

## `Malware`,

1. `Viruses`

   1. `Macro Virus` - In a scripting language for an application.

   2. `Stealth Virus`, `Polymorphic Virus`, `Self-garbling Virus` - Prevent detection from `Anti-Virus (AV)` software.

   3. `Worms` - Propagate from machine to machine in networks.

2. `Trojans` - Appears to be another program, but, it malware.

3. `Key Loggers` - Log and report user keystrokes.

4. `Remotes Access Tools (RATs)` - Software that can remotely operate the compromised machine.

   1. `Bot Nets` / `Zombies` - A controllable set of compromised machines.

5. `Firmware/OS Root Kits` - Infect the firmware or operating system kernel so they are undetectable.

6. `Ransomware` - Hijack a machine, encrypt the data, charge for the data to be decrypted.

7. `Malvertisement` - Internet advertisements that contain a chain of scripts that install malware on the target machine.

8. `Drive-by-Attacks` - Visiting a website that contains code to install malware on the target machine.

9. `Spyware` - Intelligence gathering malware. To compromise `anonymity`.

   1. `Adware` - Force advertisements and browser hijacking.

10. `Scareware` - Fake advert forcing you to pay money for some service or product.

11. `Potentially Unwanted PRograms (PUPs)` - Catch all for probably unwanted software.

12. `CPU Hijackers / Cryptojackers` - Uses CPU to perform crypto-mining validation. Attack vectors include: applications, JavaScript.

---

## Phishing / Vishing / SMSing

1. `Phishing` - Attempt to trick a user into clicking on a link a navigating to a site they do not expect.

   1. `Obfuscated Domains` https://mynet.com/.google.com

   2. `Miss-spelling` - https//:www.rnicrosoft.com

   3. `IDN Homograph` - https://www.goog1e.com

   4. `HTML Hidden Link` - <a href="https://www.goog1e.com">https://www.google.com</a>

   > These urls might contain embedded script tags to perform `Cross Site Scripting (CSS)` attacks, such as embedding a login `iframe` to get account details.

2. `Vishing` - _Phone_ or _Voice_ phishing.

3. `SMSing` - _SMS_ phishing.

---

## Spamming

1. `Spamming` - High broadcast, high volume e-mail distribution to trick a user.

---

## Doxing

1. `Doxing` - Performing research on an individual or organisation to obtain information they may not wish to be made public, or, for other purposes.

---

## Social Engineering / Scams / Fraud

1. `Social Engineering` - Trying to obtain information by pretending to be a different person.

2. `Scam` - Paying money for a product or service that does not exist, or, is different than advertised.

---

## Darknet / Dark Web

1. A `darknet` is an `encrypted overlay network` that requires specialised tools to access it.

    1. `The Onion Router (TOR)` - Implements a darknet.

    2. Other Examples: `Retro Share`, `12P Anonymous`, `GNU Net Framework`, `Freenet`, etc.

    > Not a panacea for privacy or anonymity.

2. `Dark Markets` - Probably dogey stuff.

---

## Spying and Hardware Attacks

1. Individuals or organisations with enough resources are capable of performing _spy like_ attacks using:

    1. `Small Hardware Spying Devices` - e.g. `ANT Catalogue`.

    2. `Firmware Root Kits`.

---

## Backdoors

1. `Trust`- Can we trust the operating systems and application we use?

2. A `backdoor` is a mechanism that weakens or removes a `security control`.

    1. An `unintentional backdoor` can be introduced accidentally as a `bug`.

3. __Mitigations__ include:

    1. `Keep Software Simple` - Keep the software simple. This is not always possible.

    2. `Formal Methods` - Attempting to prove the software is bug free. It is often prohibitively too time consuming and expensive.

    3. `Open Source` - Anyone can view the source.

    4. `Hashed Repeatable CI/CD` - Builds are repeatable and hashed.

        * [Reproducible Builds](https://reproducible-build.org) - A build is reproducible if given the same source code, build environment and build instructions, any party can recreate bit-by-bit identical copies of all specified artifacts.

        * No OS has yet achieved this status [Debian](https://wiki.debian.org/ReproducibleBuilds) is making progress.

        > Build tools might also need to be signed to ensure no backdoors are added by compromised compilers and other build tools.

    5. `Provenance Signed Binaries` - Binaries are signed.

    6.  __Defence in Depth__ - `Distribute trust`, create `isolation`, `reduce attack surfaces`, use `layers of defences`, etc.

---

## Resources

* [152 Simple Steps to stay safe online](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/46306.pdf) - Google report.

* [Though a PRISM Darkly](https://www.youtube.com/watch?v=_P1NA29X7Mw)
