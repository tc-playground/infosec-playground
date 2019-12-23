# Encryption and Crypto Systems

## Introduction

1. `Encryption` is a method of _transforming_ readable `ciphertext` into unreadable `ciphertext`.

2. `Decryption` is a method of _transforming_ unreadable `ciphertext` into readable `ciphertext`.

3. `Encryption` is essential for `privacy`.

4. `Encryption keys` can be used to `prove identity`.

5. `Crypto Systems` offer the following services:

    1. `Confidentially` - You can ensure no other parties can see the data being transferred.

        * Symmetric Encryption, Public Key Asymmetric Encryption.  

    2. `Authentication` - You can confirm who entities are.

        * Private Key Asymmetric Encryption.

    3. `Nonrepudiation` - You can prove that some entity sent some information.

        * Private Key Asymmetric Encryption, Hash Functions, Digital Signatures.

    4. `Integrity` - You can confirm that no other parties have altered the data being transferred.

        * Hash Functions, Digital Signatures.

6. `Public Key Cryptography (PKI)` - The framework for maintaining `privacy` and `authenticity`.

---

## Symmetric Encryption - How to securely transfer data without anyone snooping in?

1. `Symmetric Encryption` uses a single `key` and an `algorithm`.

    1. __Algorithm (Lock)__ - A mechanism that when supplied the `key` and `plaintext` can effectively produce `ciphertext` or the reverse.

        1. `Symmetric Algorithms` use a `single key`.

        2. The greater the `bit space` of the algorithm the more secure it is, but, also the slower it is to perform encrypt/decrypt operations.

        3. The algorithm use a mixture `substitutions` and `transpositions` of input.

        4. Strong `symmetric algorithms` include: `AES-256`.

    2. __Key__ - The secret component that is required to perform the transformations. The `password` becomes the `key`. 

        1. This should be generated from a `long random password` with `high entropy`.

        2. Create via a `key derivation algorithm`.

2. `Symmetric encryption` can be __attacked__ in various ways:

    1. __Brute Force__ - Systematically guessing the password and testing it.

        > This can be done effectively using clusters of custom hardware like graphics cards.

    2. __Dictionary__ - Use a dictionary of `common passwords` to guess the password.

    3. __Hybrid__ - Combine a `brute force` and `dictionary` attack.

3. `Symmetric encryption` is good for `bulk data at rest` and `bulk data transfer` - if the `key` can be safely shared.

    1. `Symmetric encryption` is _fast_ compared to `Asymmetric encryption`.

    2. `Symmetric encryption` requires that all parties have access to the single key. It can be hard to safely distribute this key.

---

## Asymmetric Encryption - How prove who you are and share keys?

1. `Asymmetric Encryption` uses `two paired keys (public private keypair)` and an `algorithm`.

    1. __Public Key__ - This is key is public, known to everyone, and, can be freely shared and distributed.

        1. __Confidentiality__  - The `public key` can be used to encrypt a secret such that only the `owner` of `public key` the decrypt and read it.

    2. __Private Key__ - Should be kept secret.

        1. __Authentication__ - The `private key` can be used to encrypt (`sign`) a secret such that if another party can decrypt it with the `public key` they can confirm the __identity__ of the issuer.
    
    3. The two keys (`key pair`) are _mathematically related_ and have to be generated at the same time.

        1. Data encrypted with the `public key` can only be decrypted with the `private key`.

        2. Data encrypted with the `private key` can only be decrypted with the `private key`.

2. `Asymmetric Encryption` allows for:

    1. __Confidentiality__

        1. The `Sender` encrypts a message with the `Receivers` __public key__ and sends the encrypted message.

        2. The `Receiver` can decrypts the message because they have the __private key__. 

            * `Confidentially` is maintained.

            * `Authenticity` is not maintained. Anyone can have access to the `public key`. 
    
    2. __Authentication__

        1. The `Sender` encrypts a message with their own __private key__ and sends the encrypted message.

        2. The `Receiver` can decrypts the message because they have the `Senders` __public key__. 

            * `Confidentially` is NOT maintained. Anyone can decrypt the message as the `public key` is public.

            * `Authenticity` IS maintained. Only the `Sender` could have signed with the `private key`.

    3. __Key exchange and Agreement__ - `Asymmetric encryption` can be used be used as part of a process to `establish a symmetric encryption key`.

        * e.g. `TLS session key.`

    2. __Digital Signatures__ - `Asymmetric encryption` can be used be use to establish a digital signature.

3. `Symmetric encryption` can be __attacked__ in various ways:

    1. __Man in the Middle (MITM)__.

* __Algorithms__ - `RSA (Rivest-Shamir-Adleman)`, `EC (Elliptic curve cryptosystem)`, `DH (Diffie-Hellman)`, `El Gamal`.

    1. The algorithms (in general) work by factoring a large number into its primes such that it can only be easily achieved if the key is known; or another similar task.

    2. `Diffie-Hellman` has the `forward secrecy` property.

> Sign with the Senders private key for AUTHENTICATION / NON-REPUDIATION.

> Sigh with the Receivers public key for CONFIDENTIALLY / INTEGRITY.

---

## Hybrid Crypto Systems - How to safely share sessions keys?

1. `Hybrid Crypto Systems` - Used a mixture of `symmetric` and `asymmetric` encryption along with agreed protocols to create a suite of crypto services.

    1. __HTTPS and SSL/TLS__.

    2. __PGP__.

---

## Hash Functions - How to detect unintentional modifications to data?

1. `Hash Functions` take __input of any size__ and generates a unique `hash` or `digest` of the input content.

2. `Hash Functions` are `one way function`. It is not possible to recreated the `input` from a `hash`.

3. `Hash Functions` can maintain the `integrity of data`.

4. `Hash Functions` should be used to generate and store the `hash of a password` instead of the `password` itself.

5. `Hash Functions` are used to implement `Hash based Message Authentication Codes (HMAC)`.

    1. `JWT` can use the `hash` of a `pre-agreed shared secret key` in all messages sent between a sender and receiver.

---

## Digital Signature - How to detect if some data is unmodified and from a known party?

1. `Digital Signatures` are a `hash` of some `input` that has encrypted with the `Senders private key`.

    1. `INPUT --Hash Algorithm--> HASH --Senders Private Key Encryption--> DIGITAL-SIGNATURE`

    2. The Receiver can decrypt the DS with the Sender's PublicKey to obtain the hash of the content and check it has not bee altered.

2. `Digital Signatures` provide __authentication__, __nonrepudiation__, and __integrity__ (if target is also encrypted).

3. `Digital Signatures` can be used with `software`, `drivers`, `certificates`, etc.

    * For example, in a web browser we can check that a `certificate` is valid and has been issued by the `CA` without tampering.

4. Checking a `Digital Signature` for signed data:

    1. Find the `public key` of the `subject` who created the `signature` and use it `decrypt` the `hash`.

    2. `Verify` the `public key` is valid against it's `x509 digital certificate`. 

    3. Using the same hashing algorithm as `signature`, generate the `hash` of the target and check it is the same.

---

## Certificate Authorities (CA) and Digital Certificates - How do we know that a public key is legitimate?

1. How do we know that a `public key` is legitimate?

    > How do we stop a MITM sending us a fake public key pretending to be __'Bob'__?

2. There a various ways a `public key` can be signed by a `trusted authority` to produce an `x509 certificate` to prove the identity of the owner of the `public key`.

    1. `Self Signed` - Insecure. Anyone can `self sign` a public key to generate a `x509 digital certificate`.

    2. `Automated` - Using an automated `CA` service.

    3. `High Security` - Using a `CA` service that performs additional background checks and auditing.

2. `x509 certificates` are used to establish a `Chain of Trust` from a `root certificate` to verify a `public key` belongs to a particular `host` or `entity`.

3. `x509 certificates` are a digital document representing information about the `subject` of a `public key` and the `issuer` who claims it.

    1. `x509 certificates` contain information regarding:

        1. __Issuer__ - `Common Name`, (Identifier).

        2. __Subject__ - `Common Name`, Public Key Info, (Identifier).

            1. A certificate is only valid for one `Common Name` (usually the `domain` - e.g. `some-site.com`).

            2. Even though only valid for one `Common Name`.

                1. `Subject Alternative Names (SANS)` may be specified. 

                2. `Wildcard Names` (e.g. `*-some-site.com`) can be used.

        3. __Validity__ - A date range of when the certificate is valid.

        4. __Signature__ - A cryptographic digital signature to prove who signed the certificate.

        5. __Certificate Hierarchy__ - The `Chain of Trust` to the `Root CA`.

    2. `x509` example:

        ```
        Certificate
            Version Number
            Serial Number
            Signature Algorithm ID
            Issuer Name
            Validity period
                Not Before
                Not After
            Subject name
            Subject Public Key Info
                Public Key Algorithm
                Subject Public Key
            Issuer Unique Identifier (optional)
            Subject Unique Identifier (optional)
            Extensions (optional)
                ...
        Certificate Signature Algorithm
        Certificate Signature
        ```

4. `x509 digital certificates` assume a __strict hierarchical__ system of certificate authorities (CAs) for issuing the certificates.

    > NB:  `PGP` uses a `web of trust` model.

    1. `x509 certificates` are provided by `Certificate Authorities`.

    2. The `x509 certificate` at the root of the chain is called the `Root Certificate` and is provided by the `Root CA`.

    3. Trusted `Root CA certificates` are automatically added to `browsers` and `operating systems` by the publishers.

5. `x509 certificates` can exists in various formats:

    1. `.pem (Privacy-enhanced Electronic Mail)` - Base64 encoded DER certificate, enclosed between "-----BEGIN CERTIFICATE-----" and "-----END CERTIFICATE-----".

    2. `.cer`, `.crt`, `.der` – usually in binary DER form, but Base64-encoded certificates are common too (see .pem above).

    3. `.p7b`, `.p7c` – `PKCS#7` SignedData structure without data, just certificate(s) or CRL(s).

    4. etc.

__References__

    1. [x509 - Wikipedia](https://en.wikipedia.org/wiki/X.509)


---

## Public Key Cryptography Infrastructure (PKI)

1. In practice `public key pairs` are not used in their raw form. They are instead encapsulated in a `signed digital certificate` with a chains of trust to a `Root CA` via `digital signatures`.

2. `https` relies on `certificates` and `chain of trust`.

3. A set of trusted `RootCA` certificates are included with `operating systems` and `browsers`.

4. If a `fake certificate` can be created then `SSL` / `TLS` is worthless and anyone can create a fake trusted certificate and snoop on supposedly secure traffic.

    1. This is a big problem for `intermediate certificate authorities`.

    2. Too many trusted `CA`s.

    3. Nation State influence.

    4. This ia major weakness of `SSL` / `TLS`.

5. `x509 certificate` standard is weak.

6. __Defences__

    1. Remove certificates based ont eh websites you are accessing.
    
    2. `SSL pinning` if you control the server - Only accept `one specific public key` - prevents a user. e.g. Banking apps.

    3. Being `anonymous` - Even if privacy is compromised you can be anonymous.

6. __Tools__ - [SSL Sniff](https://moxie.org/software/sslsniff/)

> HTTP certificates cannot be fully relied on. `SSL` / `TLS` end-to-end encryption cannot really be trusted..

---

## SSL/TLS

1. `SSL` / `TLS` can be used to negotiate as secure encrypted channel over any protocol: `https`, `ftps`, `vpn`, etc.

2. `SSL` / `TLS` uses `asymmetric encryption` to negotiate a `shared secret symmetric session key` for encrypted communication.

3. `SSL` / `TLS` provides __privacy__ as it performs end to end symmetric encryption.

    1. A `shared secret` is negotiated at the start of each session for AES symmetric encryption.

4. `SSL` / `TLS` provides __authenticity__ as it uses `public key cryptography` to check the endpoint has an identifying `private key`.

5. `SSL` / `TLS` provides __integrity__ as it uses `HMAC` codes to sign each packets of data being sent.

6. `SSL` / `TLS` provides sets of `ciphersuites` each of which offers a different set of security services.

    1. The `ciphersuite` to use is established when the connection is set up, and, is dependent on what the server and client both support.

        1. Symmetric Algorithm - e.g. `AES-256`

        2. Asymmetric Algorithm - e.g. `Diffie-Hellman`

        3. Hash Function - e.g. `HMAC-SHA256`

    2. Some `ciphersuites` support `forward secrecy` (Diffie-Hellman).

        * `forward secrecy` is the property that the clients `session keys` will not be compromised even if the `server private key` is compromised.

            > If the server private key is compromised, any old encrypted traffic cannot be decrypted.

        * If a `session key` is compromised, it will only compromise that session.

7. `SSL` / `TLS` can utilise `Server Name Indication (SNI)`.

    1. This a `TLS extension` that is used in the `handshake phase` where the `client` declares which `host/domain name` it is connecting to in _clear text_.

    2. This allows a server to present multiple certificates on the same `IP:port` address to allow multiple sites to be hosted on the same `IP:port` address without having to share the same `certificate`.

    > This is a `privacy` concerns as it allows eavesdropper to see what sites your are going to and can be used for censorship purposes.

7. `SSL / TLS` can be __vulnerable__ to:

    1. `Bad Servers` - Old, poorly configured, and, unpatched servers with bad ciphersuite options. `Heartbleed`, etc.

    2. `Bad Clients` - Old, poorly configured, and, unpatched clients with bad ciphersuite options. `Heartbleed`, etc.

    3. `MITM Attacks` - `SSL/TLS stripping`, etc.

7. References

    1. [SSL/TLS - Wikipedia](https://en.wikipedia.org/wiki/Transport_Layer_Security)

    2. [SSL/TLS Handshake](https://www.cloudflare.com/learning/ssl/what-happens-in-a-tls-handshake/)

    3. [SSL/TLS - ciphersuites](https://wiki.mozilla.org/Security/Server_Side_TLS)

    3. [Server SSL Configuration](https://weakdh.org/sysadmin.html)

---

## SSL / TLS Striping and MITM Attacks

1. `Man in the Middle (MITM)` - A situation when another entity is in position to intercept traffic between a `Sender` and `Receiver`.

    1. A `MITM` could perform various `attacks` on the data being transferred.

2. `SSL / TLS Stripping`

    1. The MITM acts as `proxy`, then erminates the `SSL/TLS` connection coming from each `Sender` and `Receiver` to decrypt traffic.

        1. Look for a `302 redirect` and `direct` requests to `https` endpoints.
        
        2. Proxy requests:

            1. Pretend to be `browser` to `server`.

            2. Pretend to be `server` to `browser`.
        
    > NB: There will not be the `https` protocol shown in the browser when intercepted.

    2. The best defences are:

        1. Checking `https` protocol is present in browser.

        2. Avoid using `wireless hot-spots`.

        3. Use a `VPN` / `End-to-End Encryption`.

        4. Monitor Ethernet with `ARP watch` or `sniffdet`for ARP spoofing or poisoning.

        5. Use `Virtual LANS (VLAN)` and other methods of `network isolation` using a `switch`, firewalls, separate WiFi networks, etc.

        6. On the server enable `HTTP Strict Transport Security (HSTS)` - to send an HTTP header that tells the browser to enforce `https`.

3. It may be difficult to obtain a `MIM` position unless the attacker controls the network:

    1. Nation State, ISP, Company Network, etc.

    2. WiFi compromised, LAN `ARP poisoning`, etc.

4. `ARP Cache poisoning` - `ARP` has no _authentication mechanism_, so, any attacker can pretend to be the networks `default gateway` and proxy traffic.

    1. `Rogue Access Points` - Using a `fake access point` with SSL/TLS stripping enabled.

5. __References__

    1. [Intro to Sniffers](http://www.irongeek.com/i.php?page=security/AQuickIntrotoSniffers)

    2. [Monitor ARP activity](https://www.tecmint.com/monitor-ethernet-activity-in-linux/)

6. __Tools__

    1. [SSL Strip](https://moxie.org/software/sslstrip)

    2. [Ettercap](https://www.ettercap-project.org)

    3. [Arp Spoof](https://linux.die.net/man/8/arpspoof)

---

## VPNs and End to End Encryption

1. `VPN`s allow you `tunnel` to protect your `anonymity`.

2. `PGP`

3. `SSL` / `TLS`

4. `ZRTP`

5. `OTR`