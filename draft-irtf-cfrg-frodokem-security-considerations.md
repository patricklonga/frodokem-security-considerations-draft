---
title: "Security Considerations for FrodoKEM"
abbrev: "FrodoKEM Security Considerations"
category: info

docname: draft-irtf-cfrg-frodokem-security-considerations-00
submissiontype: IRTF
date: 2026-11-09
v: 3
ipr: trust200902
workgroup: CFRG
pi: [toc, sortrefs, symrefs]
keyword:
 - FrodoKEM
 - PQC
venue:
  group: Working Group
  repo: github.com/patricklonga/frodokem-security-considerations-draft

author:
 -
    fullname: Patrick Longa
    organization: Microsoft
    email: plonga@microsoft.com
 -
    fullname: Joppe W. Bos
    organization: NXP Semiconductors
    email: joppe.bos@nxp.com
 -
    fullname: Stephan Ehlen
    organization: Federal Office for Information Security (BSI)
    email: stephan.ehlen@bsi.bund.de
 -
    fullname: Douglas Stebila
    organization: University of Waterloo
    email: dstebila@uwaterloo.ca

normative:
  I-D.FrodoKEM:
    title: "FrodoKEM: key encapsulation from learning with errors (IETF Internet-Draft, draft-longa-cfrg-frodokem)"
    author:
    - name: P. Longa
    - name: J. W. Bos
    - name: S. Ehlen
    - name: D. Stebila
    date: 2026-03
    target: https://datatracker.ietf.org/doc/draft-longa-cfrg-frodokem/
  ISO18033-2-AMD2:
    title: "ISO/IEC 18033-2:2006/Amd 2, Information technology — Security techniques — Encryption algorithms — Part 2: Asymmetric ciphers, Amendment 2"
    author:
    - name: ISO
    date: 2026-06
    target: https://www.iso.org/standard/86890.html

informative:
  FrodoSpec2021:
    title: "FrodoKEM: Learning With Errors Key Encapsulation, Algorithm Specifications And Supporting Documentation (FrodoKEM Round 3 specification)"
    author:
    - name: E. Alkim
    - name: J. W. Bos
    - name: L. Ducas
    - name: P. Longa
    - name: I. Mironov
    - name: M. Naehrig
    - name: V. Nikolaenko
    - name: C. Peikert
    - name: A. Raghunathan
    - name: D. Stebila
    date: 2021-06
    target: https://frodokem.org/files/FrodoKEM-specification-20210604.pdf
  FrodoAnnex:
    title: Annex on FrodoKEM updates
    author:
    - name: E. Alkim
    - name: J. W. Bos
    - name: L. Ducas
    - name: P. Longa
    - name: I. Mironov
    - name: M. Naehrig
    - name: V. Nikolaenko
    - name: C. Peikert
    - name: A. Raghunathan
    - name: D. Stebila
    date: 2023-04
    target: https://frodokem.org/files/FrodoKEM-annex-20230418.pdf
  FrodoPaper2025:
    title: "FrodoKEM: A CCA-Secure Learning With Errors Key Encapsulation Mechanism"
    author:
    - name: L. Glabush
    - name: P. Longa
    - name: M. Naehrig
    - name: C. Peikert
    - name: D. Stebila
    - name: F. Virdia
    date:  2025-10
    target: https://eprint.iacr.org/2025/1861.pdf
  MLKEM-SC:
    title: ML-KEM Security Considerations (IETF Internet-Draft, draft-sfluhrer-cfrg-ml-kem-security-considerations)
    author:
    - name: S. Fluhrer
    - name: Q. Dang
    - name: J. P. Mattsson
    - name: K. Milner
    - name: D. Shiu
    date: 2026-05
    target: https://github.com/sfluhrer/ml-kem-security-considerations
  ACD+18:
    title: Estimate all the LWE, NTRU schemes!
    author:
    - name: M. R. Albrecht
    - name: B. R. Curtis
    - name: A. Deo
    - name: A. Davidson
    - name: R. Player
    - name: E. W. Postlethwaite
    - name: F. Virdia
    - name: T. Wunderer
    date: 2018
    target: https://eprint.iacr.org/2018/331
  ADH+19:
    title: The General Sieve Kernel and New Records in Lattice Reduction
    author:
    - name: M. R. Albrecht
    - name: L. Ducas
    - name: G. Herold
    - name: E. Kirshanova
    - name: E. W. Postlethwaite
    - name: M. Stevens
    date: 2019
    target: https://eprint.iacr.org/2019/089
  AGP+20:
    title: Estimating quantum speedups for lattice sieves
    author:
    - name: M. R. Albrecht
    - name: V. Gheorghiu
    - name: E. W. Postlethwaite
    - name: J. M. Schanck
    date: 2020
    target: https://eprint.iacr.org/2019/1161
  DDG+20:
    title: "LWE with side information: Attacks and concrete security estimation"
    author:
    - name: D. Dachman-Soled
    - name: L. Ducas 
    - name: H. Gong 
    - name: M. Rossi
    date: 2020
    target: https://eprint.iacr.org/2020/292
  Gla24:
    title:  Tight multi-target security for key encapsulation mechanisms
    author:
    - name: L. Glabush
    date: 2024
    target: https://uwspace.uwaterloo.ca/items/8871c4b1-c2c6-4a42-9485-1466f1772985
  GHS25:
    title:  Tight multi-target security for key encapsulation mechanisms
    author:
    - name: L. Glabush
    - name: K. Hövelmanns
    - name: D. Stebila
    date: 2025
    target: https://eprint.iacr.org/2025/343
  BSI24:
    title: "Cryptographic Mechanisms: Recommendations and Key Lengths, BSI TR-02102-1, Version: 2024-1"
    author:
    - name: Federal Office for Information Security (BSI)
    date: 2024-01
    target: https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/TechGuidelines/TG02102/BSI-TR-02102-1.pdf?__blob=publicationFile&v=7
  ANSSI23:
    title: ANSSI views on the Post-Quantum Cryptography transition (2023 follow up)
    author:
    - name: National Cybersecurity Agency of France (ANSSI)
    date: 2023
    target: https://cyber.gouv.fr/en/publications/follow-position-paper-post-quantum-cryptography
  AIVD24:
    title:  "The PQC Migration Handbook: Guidelines for Migrating to Post-Quantum Cryptography (second edition)"
    author:
    - name: General Intelligence and Security Service (AIVD) and Centrum Wiskunde & Informatica (CWI) and Netherlands Organization for Applied Scientific Research (TNO)
    date: 2024
    target: https://publications.tno.nl/publication/34643386/fXcPVHsX/TNO-2024-pqc-en.pdf
  NIST-3rd-round:
    title: Status Report on the Third Round of the NIST Post-Quantum Cryptography Standardization Process
    author:
    - name: National Institute of Standards and Technology (NIST)
    date: 2022-07
    target: https://nvlpubs.nist.gov/nistpubs/ir/2022/NIST.IR.8413-upd1.pdf
  FrodoCode:
    title: Reference C and Python implementations of FrodoKEM and eFrodoKEM
    author:
    - name: E. Alkim
    - name: J. W. Bos
    - name: L. Ducas
    - name: P. Longa
    - name: I. Mironov
    - name: M. Naehrig
    - name: V. Nikolaenko
    - name: C. Peikert
    - name: A. Raghunathan
    - name: D. Stebila
    date: 2017-2026
    target: https://github.com/microsoft/PQCrypto-LWEKE
  Botan:
    title: "Botan: Cryptography Toolkit"
    date: 2001-2026
    target: https://botan.randombit.net/
  NIST-SP800-227:
    title: Recommendations for Key-Encapsulation Mechanisms (NIST Special Publication 800, NIST SP 800-227)
    author:
    - name: G. Alagic
    - name: E. Barker
    - name: L. Chen
    - name: D. Moody
    - name: A. Robinson
    - name: H. Silberg
    - name: N. Waller
    date: 2025-09
    target: https://doi.org/10.6028/NIST.SP.800-227

--- abstract
  ISO standardized FrodoKEM in June 2026 [ISO18033-2-AMD2]. This document provides
  security guidance for FrodoKEM for use in protocols. It explains what security
  claims protocol designers may rely on, what assumptions and conditions are
  required, what parameter sets are in scope, and what implementors need to do
  to use FrodoKEM safely. The scope follows the current FrodoKEM Internet-Draft
  [I-D.FrodoKEM].

--- middle

# Introduction

FrodoKEM is a conservative post-quantum key encapsulation mechanism (KEM)
whose security derives from a parameterization of the well-studied Learning
with Errors (LWE) problem. Thus, FrodoKEM's most distinctive feature is its use
of generic, algebraically unstructured lattices, which provides an additional
layer of security in case future cryptanalytic attacks are able to exploit
structured lattices.

As a key encapsulation mechanism, FrodoKEM is a three-tuple of algorithms
(key generation, encapsulation, decapsulation):

   *  Key generation is given by a randomized algorithm that takes no inputs,
      and outputs a public key and a private key;

   *  Encapsulation is given by a randomized algorithm that takes as input a
      public key, and outputs a ciphertext and a shared secret;

   *  Decapsulation is given by an algorithm that takes as input a ciphertext
      and a private key, and outputs a shared secret.

With these algorithms, two parties, Alice and Bob, can perform a two-pass
protocol to derive a shared secret as follows. First, Alice generates a
public/private keypair during key generation. In the first protocol pass,
Bob uses Alice's public key to produce a ciphertext and a shared secret
with the encapsulation algorithm. In the second protocol pass, Alice uses
her private key and the ciphertext to execute the decapsulation operation and
produce a shared secret. The shared secret is indistinguishable from random
by an adversary and can be used directly to establish a secure communication
channel using a symmetric-key algorithm.

A KEM protocol like FrodoKEM is not always a drop-in replacement for
Diffie–Hellman. Unlike Diffie–Hellman, where both parties exchange public
keys and jointly derive a shared secret (often computing intermediate values
independently and in parallel), a KEM requires a recipient’s public key
before encapsulation and produces ciphertexts bound to that specific key.
Consequently, KEMs are less flexible in asynchronous or precomputation
settings.

Nevertheless, KEMs can serve as drop-in replacements in several common
protocol patterns, as explained in the introduction of [MLKEM-SC]. In
ephemeral–ephemeral key exchange (e.g., TLS 1.3, SSH and WireGuard), or
in static–ephemeral settings where one party has a long-term public key
(e.g., ECIES and HPKE), a KEM can replace Diffie–Hellman. In contrast, KEMs
do not directly support constructions that rely on joint, bidirectional
derivation of shared secrets. This includes Diffie–Hellman ratchets (e.g.,
Signal), implicit ephemeral–static authentication patterns (e.g., Noise and
WireGuard), and static–static key establishment, where both parties hold
long-term public keys.

## Standard and Ephemeral FrodoKEM

FrodoKEM consists of two main variants:

   *  "Standard" (or "salted") FrodoKEM: this variant can freely reuse
      public/private keypairs, as it includes countermeasures that protect
      against multi-ciphertext attacks [FrodoAnnex]. Concretely, standard
      FrodoKEM doubles the length of the seed seedSE and incorporates a
      public random salt value during encapsulation.
   *  "Ephemeral" FrodoKEM (or eFrodoKEM): this variant does not include
      countermeasures against multi-ciphertext attacks and, hence, is intended
      for applications in which the number of ciphertexts produced relative to
      any single public key is small. As stated in [I-D.FrodoKEM], ephemeral
      FrodoKEM must not be used in applications in which a single public key
      may produce 2^8 ciphertexts or more.
      
Ephemeral FrodoKEM is available mostly for backwards compatibility. For most
applications, standard FrodoKEM is the recommended option, and it is the option
this document refers to, unless explicitly stated.

# Conventions and Definitions

{::boilerplate bcp14-tagged}

# Using FrodoKEM

FrodoKEM consists of three algorithms (executed in this order): key generation,
encapsulation, and decapsulation.

## Key Generation

In this first step, Alice generates a public and private keypair. The procedure
is described in Section 7.1 of [I-D.FrodoKEM].

The algorithm internally calls the random number generator (RNG) to produce seeds
s, seedSE and z (s is used as a fallback random secret, seedSE is used to sample
error/secret matrices and z is used to generate the so-called public matrix A).
The seeds (s, seedSE, z) can be securely stored to enable later reconstruction of
the fully expanded private key. These seeds must be protected as private key
material.

Intermediate data other than the matrix A should be securely deleted when no
longer needed. When there is enough storage capacity, matrix A may be saved for
repeated decapsulation operations with the same private key.

## Encapsulation

In the second step, Bob generates a ciphertext and a shared secret. The procedure
is described in Section 7.2 of [I-D.FrodoKEM].

The algorithm internally requires fresh randomness to generate the message value u 
and the public salt. The value u is secret encapsulation randomness. 
The salt is released as part of the ciphertext and is intended to be public, but it 
must be freshly generated with sufficient entropy and must be independent of u.
Implementations must use a cryptographically secure RNG or DRBG whose public outputs
do not compromise past or future secret outputs.

Intermediate data other than data corresponding to the ciphertext or public key
(including matrix A) should be securely deleted when no longer needed. When there
is enough storage capacity, matrix A may be saved for repeated encapsulation
operations with the same public key.

The ciphertext can be sent back to Alice; if the protocol is successful, the
shared secret will be the key shared with Alice.

## Decapsulation

In the third and final step, Alice generates the shared secret using her private
key and the ciphertext sent by Bob. The procedure is described in Section 7.3 of
[I-D.FrodoKEM].

The algorithm reconstructs the ciphertext that would result from the decoded
message and compares it with the received ciphertext. If the comparison fails, 
decapsulation uses the fallback secret s to derive the shared secret. This
implicit-rejection step is essential for CCA security and must not be skipped,
exposed as a distinguishable error, or implemented with timing, memory-access,
logging, or control-flow behavior that reveals whether the received ciphertext
was valid. The comparison of the reconstructed and received ciphertext
components and the selection between k' and s must be performed in constant time
with respect to the secret key, the decoded candidate message, and the comparison
result.

Intermediate data other than data corresponding to the ciphertext sent by Bob or
to matrix A should be securely deleted when no longer needed.

If the protocol is successful, the shared secret generated by Alice and Bob will
be the same.

# Parameter Sets

Standard FrodoKEM includes six parameter sets:

1. FrodoKEM-640-⟨PRG⟩, which matches or exceeds the brute-force security of AES128.

2. FrodoKEM-976-⟨PRG⟩, which matches or exceeds the brute-force security of AES192.

3. FrodoKEM-1344-⟨PRG⟩, which matches or exceeds the brute-force security of AES256.

The options for ⟨PRG⟩ are AES or SHAKE, when either AES128 or SHAKE128,
respectively, is used for the generation of matrix A. Thus, FrodoKEM consists
of the parameter sets FrodoKEM-640-AES, FrodoKEM-976-AES, FrodoKEM-1344-AES,
FrodoKEM-640-SHAKE, FrodoKEM-976-SHAKE and FrodoKEM-1344-SHAKE.

The AES variants are suitable for platforms featuring AES hardware acceleration
(such as AES-NI on Intel platforms), while the SHAKE variants generally provide
competitive or better performance in comparison with the AES variants in the
absence of such hardware acceleration.

Table 1 summarizes the input and output sizes for the different FrodoKEM parameter
sets.

|     Scheme     |  secret key sk  |  public key pk  |  ciphertext ct  | shared secret ss |
|---------------:|:---------------:|:---------------:|:---------------:|:----------------:|
|   FrodoKEM-640 |      19,888     |       9,616     |       9,752     |        16        |
|   FrodoKEM-976 |      31,296     |      15,632     |      15,792     |        24        |
|  FrodoKEM-1344 |      43,088     |      21,520     |      21,696     |        32        |
{: title="Sizes (in bytes) of inputs and outputs for the FrodoKEM parameter sets."}

Similarly, ephemeral FrodoKEM consists of six parameter sets, each analogous
to the standard FrodoKEM variants above. Thus, ephemeral FrodoKEM consists of
the parameter sets eFrodoKEM-640-AES, eFrodoKEM-976-AES, eFrodoKEM-1344-AES,
eFrodoKEM-640-SHAKE, eFrodoKEM-976-SHAKE and eFrodoKEM-1344-SHAKE.

Table 2 summarizes the input and output sizes for the different ephemeral FrodoKEM
parameter sets. All the sizes are identical to standard FrodoKEM, with the exception
of the ciphertexts, which do not include the salt value.

|     Scheme     |  secret key sk  |  public key pk  |  ciphertext ct  | shared secret ss |
|---------------:|:---------------:|:---------------:|:---------------:|:----------------:|
|  eFrodoKEM-640 |      19,888     |       9,616     |       9,720     |        16        |
|  eFrodoKEM-976 |      31,296     |      15,632     |      15,744     |        24        |
| eFrodoKEM-1344 |      43,088     |      21,520     |      21,632     |        32        |
{: title="Sizes (in bytes) of inputs and outputs for the ephemeral FrodoKEM parameter sets."}

The complete set of parameters that characterizes each parameter set is
listed in Section 9.1 of [I-D.FrodoKEM].

## Parameter-Set Selection and Defaults

For most applications, the default choice should be one of the standard
(salted) FrodoKEM variants, not an ephemeral variant, unless the protocol
can guarantee that fewer than 2^8 ciphertexts are ever produced under a
public key.

It is recommended to use the highest security level supported by a given
application. For most applications, it is recommended to use either
FrodoKEM-976 or FrodoKEM-1344. FrodoKEM‑640 may be used in applications
that cannot accommodate the performance or bandwidth requirements of the
higher parameter sets and do not require long-term confidentiality.

A short decision guide is therefore:

* choose **standard FrodoKEM**, not eFrodoKEM, by default;
* choose **FrodoKEM-976** or **FrodoKEM-1344** for most applications;
* choose **FrodoKEM-640** only when short-term security is the intended
  use case;
* choose **AES** variants if the target environment has AES acceleration;
  otherwise, **SHAKE** is a reasonable choice.

# Is FrodoKEM Safe to Use?

## Authoritative Specifications

For protocol designers and implementors, the authoritative FrodoKEM
specification is detailed in the FrodoKEM Internet-Draft [I-D.FrodoKEM].
As of version draft-longa-cfrg-frodokem-03, the FrodoKEM I-D is fully
aligned with the ISO standard [ISO18033-2-AMD2], with the sole exception
that the FrodoKEM-640 parameter set is **not** included in
[ISO18033-2-AMD2]. In addition, the FrodoKEM I-D specifies a seed-based
private key format as an optional serialization method (Section 7.1 of
[I-D.FrodoKEM]), whereas [ISO18033-2-AMD2] does not describe this option.

Both documents are in turn derived from FrodoKEM's Round 3 specification
[FrodoSpec2021] and the 2023 annex that provides the algorithm specification
and the salted update materials [FrodoAnnex].

## Security Notions and Security Strength

For protocol use, the relevant cryptographic notion is IND-CCA2 KEM
security. In practice, this means that users can freely reuse public/private
keypairs for multiple encapsulation/decapsulation operations (this applies
specifically to the case of standard FrodoKEM).

A related notion is multi-target security, in which the adversary is
given multiple ciphertexts, each generated under a public key of its
choice. The 2025 FrodoKEM paper [FrodoPaper2025] proves that FrodoKEM
tightly achieves multi-target security by means of the salted
Fujisaki-Okamoto (SFO) transform in conjunction with the hashing of the
public key in the computation of random strings during encapsulation.

FrodoKEM's Round 3 specification [FrodoSpec2021] provides a security
proof that shows that the IND-CCA2 security of FrodoKEM is tied to the
security of concrete instances of the decisional normal-form LWE problem
in the classical ROM. A similar (non-tight) proof is given in the QROM.
These results were revisited in the 2025 FrodoKEM paper [FrodoPaper2025].

As is customary in cryptography, security strength is better quantified
by an analysis of the best-known cryptanalytic attacks against a given
cryptographic scheme. An up-to-date cryptanalysis of FrodoKEM LWE
instances was carried out in [FrodoPaper2025]. The results for the
'beyond-core-SVP' methodology showed security estimates of 149.8 bits
for (e)FrodoKEM-640, 212.6 bits for (e)FrodoKEM-976 and 266.8 bits for
(e)FrodoKEM-1344, which support the security level claims for the
FrodoKEM parameter sets.

## Basis for Confidence

The LWE problem, which underlies the security of FrodoKEM, has been
extensively studied for about two decades. Examples of cryptanalysis
papers include [ACD+18], [ADH+19], [AGP+20], [DDG+20], to name a few.

FrodoKEM has a substantial public record that dates back to the start
of NIST's Post-Quantum Cryptography Standardization process in 2017.
In addition to the security analysis presented as part of the NIST
submission, FrodoKEM's security has been studied in [Gla24], [GHS25]
and [FrodoPaper2025]. 

FrodoKEM was selected as a third-round alternate candidate, and
ultimately was not selected by NIST due to performance reasons, as
explained in Section 4.3.1 of [NIST-3rd-round]. In that same report,
NIST acknowledges that "In terms of security, Frodo’s conservative
design choices are laudable".

FrodoKEM's conservative design has gained the support of multiple
government agencies, which have emphasized the need for a conservative
option with less underlying algebraic structure. FrodoKEM has been
recommended as a conservative alternative by the German BSI [BSI24],
the French ANSSI [ANSSI23], and the Dutch NLNCSA and AIVD [AIVD24].
This support ultimately led to the standardization of FrodoKEM by ISO
[ISO18033-2-AMD2]. 

## Protocol-Relevant Considerations

As a KEM, FrodoKEM does not provide authentication of the communicating
parties. Therefore, the surrounding protocol must ensure authentication
of public keys and must bind protocol messages to the identities of the
participating parties. This is typically achieved using digital
signatures or authenticated key exchange constructions.

Similar to ML-KEM, FrodoKEM employs implicit rejection: when
decapsulation is performed on an invalid ciphertext, it returns a
pseudorandom shared secret rather than signaling an error. As a result,
the communicating parties may derive different shared secrets. In
well-designed authenticated key exchange protocols, where the derived
shared secret is used to produce symmetric cryptographic keys, such a
mismatch causes subsequent protocol steps (e.g., key confirmation or
integrity checks) to fail without compromising security.

Likewise, FrodoKEM has a (negligible) probability that decapsulation
of a valid ciphertext does not recover the same shared secret produced
during encapsulation. This failure probability is extremely small for
the standardized parameter sets and is accounted for in the security
analysis. In practice, such an event results in a mismatch between
the parties’ derived shared secrets. As discussed above, in
well-designed protocols that derive symmetric keys from the shared
secret, this mismatch causes subsequent integrity checks or key
confirmation steps to fail, leading to a safe termination of the
protocol without compromising security.

Implementations must validate the exact lengths of public keys, secret
keys and ciphertexts for the selected parameter set before any further
processing. The FrodoKEM Internet-Draft presents fixed formats and does
not describe flexible wire encodings for these values.

It is safe to reuse (standard) FrodoKEM public keys for multiple
encapsulations, and doing so produces independent shared secrets for
each ciphertext. However, this does not provide perfect forward
secrecy: if the private key is later compromised, past sessions can
be recovered. Therefore, when a protocol already transmits an
unauthenticated public key (e.g., as part of a handshake), it is
recommended to generate a fresh keypair per session and immediately
delete the private key after decapsulation to obtain perfect forward
secrecy.

Because lattice-based KEMs are relatively new compared to the classical
mechanisms they are intended to replace, deployments are encouraged to
use FrodoKEM in a hybrid construction with a traditional key-establishment
mechanism. Such use should follow a specified hybrid KEM or protocol
construction employing a security-analyzed combiner; e.g., see Section 4.6
of [NIST-SP800-227].

## Implementation security {#ImplementationSecurity}

FrodoKEM is simple to implement and facilitates writing implementations
that are compact and run in constant time. At its core, FrodoKEM
consists of simple matrix-vector operations that are easy to scale to
different matrix dimensions. Also, FrodoKEM uses a modulus q that is
either 2^15 or 2^16. These design choices enable full reuse of the
same matrix functions across parameter sets, with only parameter
instantiation required at build time.

The use of a power-of-two modulus further simplifies implementation.
Arithmetic modulo q is efficient and easy to do in constant time on
modern architectures; for example, reduction modulo 2^16 is
automatically achieved when using 16-bit data types. Moreover, the
chosen matrix dimensions are divisible by 16, facilitating vectorized
implementations and simplifying the use of AES128 for generation of
the matrix A.

Error sampling is likewise designed for simplicity and code reuse.
Across all security levels, each sample requires 16 bits, and the
corresponding discrete cumulative distribution function (CDF) tables
contain values strictly below 2^15. This allows for a uniform
inversion-sampling routine instantiated with precomputed tables.
Because these tables are small, constant-time lookup used to
mitigate timing side-channel attacks can be implemented with
negligible complexity and performance overhead.

The byte encoding rules, the separate packing/unpacking byte encoding,
and the matrix encoding and decoding rules are explicitly specified in
the current FrodoKEM Internet-Draft [I-D.FrodoKEM]. Implementations
must follow those rules exactly.

Special care should be given to the ciphertext consistency check
during decapsulation, ensuring that the implementation reads both k'
and s (the secret and the fallback random secret, resp., used
for the shared secret computation), the required comparisons are done
in a constant-time way that avoids early termination, and the final
value for kHat is set using data-independent evaluation.

In some scenarios, such as embedded applications, implementors may
need to consider additional countermeasures (e.g., masking) to protect
against more powerful side-channel attacks beyond timing attacks. While
resistance to certain classes of side-channel attacks remains an active
area of research, the simplicity of FrodoKEM’s design significantly
reduces the attack surface compared to other LWE-based schemes that
rely on FFT-based multiplication techniques.

## Public implementations

Reference [FrodoCode] provides portable and optimized implementations
of FrodoKEM written in C, as well as reference implementations written
in Python that are intended to be readable and close to a line-by-line
mapping of the FrodoKEM algorithms. These implementations include
functional tests and known answer tests.

The Botan cryptography library also contains a C++ implementation of
FrodoKEM [Botan].

# IANA Considerations

This document has no IANA actions.

--- back