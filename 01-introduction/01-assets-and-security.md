# Assets and Security

## Introduction

* `Cyber Security` is about protecting `digital assets` and everything associated with them.

---

## Assets

1. `Assets` - Valuable things to protect.

    * Privacy, Anonymity, Activity, Identity, Location, Accounts, Email, Financial, etc.

2. `Assets` need not be __physical things__. They can also be `organisational`, `people`, `processes`, `functions`, etc. 

3. Loss of control of an `asset` will lead to __consequences__. 

    * _CyberSec is the understanding and management of this `risk`_.

---

## Privacy, Anonymity, and, Pseudo-anonymity

1. `Privacy` - Protecting `content`.

2. `Anonymity` - Protecting `identity` - making `activity` non-attributable.

3. `Pseudo Anonymity` - Protecting `actual identity`. Maintain a `representation of identity`. Alias.

---

## Security, Vulnerabilities, Threats, and, Adversaries

1. `Assets` - Valuable things to protect.

    * Privacy, Anonymity, Activity, Identity, Location, Accounts, Email, Financial, etc.

2. `Security` - Protection of assets to appropriate levels, via `security controls` (technology, processes, actions).

    * OpSec, Encryption, Patching, SSH, PGP, HTTPS, TLS, 2FA, VPN, Firewall, TOR, etc.

    > __Security Process__ : `Select` -> `Implement` -> `Assess` -> `Monitor`

3. `Vulnerabilities` - `Known` and `unknown` ways that security assets are at `risk`.

    * Bugs, poor actions.

4. `Threats` - Mechanism to attack protected assets.

    * Phishing, RootKits, Viruses, RATS, Malware, Exploit Kits, Backdoors, Spying, Mass surveillance, etc.

5. `Adversaries`

    * Spies, Hackers, Crackers, Cyber Criminal, Nation States.

---

## Risk Assessments and Threat Modelling

1. __Risk__ = (_Vulnerabilities_ x _Threats_ x _Consequences_)

2. A particular `asset` has particular `security controls`, `vulnerabilities`, `threats`, and `adversaries`.

> __NB__: `Security`, `Privacy`, `Anonymity`, `Practicality` are __often in conflict__ and `security controls` need to be appropriate.

3. `Security Attributes` - Are ways of classifying `assets` to determine what `security controls` are appropriate.

    1. `CIA Triad`

        1. `Confidentiality` - Do we want the asset to be protected from unauthorised entities?

        2. `Integrity` - Do we want to protect the asset from being modified or altered by unauthorised entities?

        3. `Availability` - When/How do we make the asset to be available when it is required?
    
    2. `Parkerian Hexad` - Non-Repudiation, Possesion, Utility. Authentication. Authorisation. 
    
    3. `SABSA business attributes`.

---

## Defense in Depth

> Provide layer of defense so if one `security control` fails another `security control` can protect you.

1. `Prevention` - Protect assets with multiple `security controls`.

2. `Detection` - Detect `compromised assets`. Set up `canaries`, `honeypots`, etc.

3. `Recovery` - Have a way of recovering `compromised assets`.

---

## The Zero Trust Model

1. The less you trust, the lower your risk.

2. `Evaluate` instead of trust. 

    * `Zero Knowledge` systems?

    * `FOSS`.

3. `Distribute` your trust. Mitigate the risk.

