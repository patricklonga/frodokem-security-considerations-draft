---
title: "Security Considerations for FrodoKEM"
abbrev: "FrodoKEM Security Considerations"
category: info

docname: draft-longa-cfrg-frodokem-security-considerations-00
submissiontype: IRTF
date: 2026-05-30
v: 3
ipr: trust200902
workgroup: CFRG
pi: [toc, sortrefs, symrefs]
keyword:
 - FrodoKEM
 - PQC
venue:
  group: Working Group
  repo:

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
    title: FrodoKEM: key encapsulation from learning with errors (IETF Internet-Draft, draft-longa-cfrg-frodokem)
    author:
    - name: P. Longa
    - name: J. W. Bos
    - name: S. Ehlen
    - name: D. Stebila
    date: 2026-03
    target: https://datatracker.ietf.org/doc/draft-longa-cfrg-frodokem/
  ISO18033-2-AMD2:
    title: ISO/IEC 18033-2:2006/Amd 2, Information technology — Security techniques — Encryption algorithms — Part 2: Asymmetric ciphers, Amendment 2
    author:
    - name: ISO
    date: 2026-06
    target: https://www.iso.org/standard/86890.html

informative:
  FrodoSpec2021:
    title: FrodoKEM: Learning With Errors Key Encapsulation, Algorithm Specifications And Supporting Documentation (FrodoKEM Round 3 specification)
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
    title: FrodoKEM: A CCA-Secure Learning With Errors Key Encapsulation Mechanism
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
    title: LWE with side information: Attacks and concrete security estimation
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
  NIST-3rd-round:
    title: Status Report on the Third Round of the NIST Post-Quantum Cryptography Standardization Process
    author:
    - name: NIST
    date: 2022-07
    target: https://nvlpubs.nist.gov/nistpubs/ir/2022/NIST.IR.8413-upd1.pdf

---

--- abstract
  ISO standardized FrodoKEM in June 2026 [ISO18033-2-AMD2]. This document gives
  security guidance for FrodoKEM for use in protocols. It explains what security
  claims protocol designers may rely on, what assumptions and conditions are
  required, what parameter sets are in scope, and what implementers need to do
  to use FrodoKEM safely. The scope follows the current FrodoKEM Internet-Draft
  [I-D.FrodoKEM].

--- middle

# Introduction

FrodoKEM is a conservative post-quantum key encapsulation mechanism (KEM)
whose security derives from a parameterization of the well-studied Learning
with Errors (LWE) problem. Thus, FrodoKEM's most distintive feature is its use
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

A KEM protocol like FrodoKEM is not necessarily a drop-in replacement for
Diffie-Hellman key exchange. The same specific scenarios for which ML-KEM
works (or does not work) as Diffie-Hellman that are described in the
Introduction of [MLKEM-SC] also apply to FrodoKEM.
> Patrick: to check against definitions of standard and ephemeral FrodoKEM.  

> Patrick: should we say anything about encryption (HPKE)?


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
this document refers to, unless explictly stated.

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
These seeds can be securely stored to allow the reconstruction of the fully
expanded key format. Intermediate data other than the matrix A must be securely
deleted. When there is enough storage capacity, matrix A may be saved for repeated
decapsulation operations with the same private key.

## Encapsulation

In the second step, Bob generates a ciphertext and a shared secret. The procedure
is described in Section 7.2 of [I-D.FrodoKEM].

The algorithm internally calls the RNG to produce a random message value u and a
random public salt, which are then used to generate a ciphertext and a shared
secret. Since the salt value is released as part of the ciphertext, implementors
may want to take some precautions to avoid releasing the RNG output directly.
Intermediate data other than data corresponding to the ciphertext or public key
(including matrix A) must be securely deleted. When there is enough storage
capacity, matrix A may be saved for repeated encapsulation operations with the
same public key.

The ciphertext can be sent back to Alice; if the protocol is successful, the
shared secret will be the key shared with Alice.

## Decapsulation

In the third and final step, Alice generates the shared secret using her private
key and the ciphertext sent by Bob. The procedure is described in Section 7.3 of
[I-D.FrodoKEM].

The algorithm internally regenerates the computation of the ciphertext to make
sure it was not maliciously generated. If a ciphertext is detected to be invalid
the shared secret is produced with an unrelated random value (the fallback seed
s) that does not disclose any information. This step must not be skipped as an
attacker can carry out a chosen-ciphertext attack to reveal the private key.
Intermediate data other than data corresponding to the ciphertext sent by Bob
or matrix A must be securely deleted.

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

It is recommended that users should use the highest possible security level
that a given application allows. For most applications, it is recommended
to use either FrodoKEM-976 or FrodoKEM-1344. FrodoKEM-640 may be used in
applications that require short-term security.

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
As of version draft-longa-cfrg-frodokem-02, the I-D is fully compatible
with the ISO standard [ISO18033-2-AMD2], with the sole exception that
the FrodoKEM-640 parameter set is **not** included in [ISO18033-2-AMD2]. 

Both documents are in turn derived from FrodoKEM's Round 3 specification
[FrodoSpec2021] and the 2023 annex that provides the algorithm specification
and the salted update materials [FrodoAnnex].

## Security Notions and Security Strength

For protocol use, the relevant cryptographic notion is IND-CCA2 KEM
security. In practice, this means that users can freely reuse public/private
keypairs for multiple encapsulation/decapsulation operations (this applies
specifically to the case of standard FrodoKEM).

A relevant related notion is multi-target security. Here, the adversary is
given potentially several ciphertexts each generated under a public key
of the adversary's choice. The 2025 FrodoKEM paper [FrodoPaper2025] proves
that FrodoKEM tightly achieves multi-target security by means of the salted
Fujisaki-Okamoto (SFO) transform in conjunction with the hashing of the
public key in the computation of random strings during encapsulation.

FrodoKEM's Round 3 specification [FrodoSpec2021] provides a security
proof that shows that the IND-CCA2 security of FrodoKEM is tied to the
security of concrete instances of the decisional normal-form LWE problem
in the classical ROM. A similar (non-tight) proof is given in the QROM.
These results were revisited in the 2025 FrodoKEM paper [FrodoPaper2025].

As is customary in cryptography, security strength is better quantified
by an analysis of the best-known cryptanalytic attacks against a given
cryptographic scheme. An up-to-date cryptanalysis of FrodKEM LWE
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
In addition to the security analysis presented as part of the the NIST
submission, FrodoKEM' security has been studied in [Gla24], [GHS25]
and [FrodoPaper2025]. 

FrodoKEM was selected as a third-round alternate candidate, and
ultimately was not selected by NIST due to performance reasons, as
explained in Section 4.3.1 of [NIST-3rd-round]. In that same report,
NIST acknowledges that "In terms of security, Frodo’s conservative
design choices are laudable".

FrodoKEM's conservative design has gained the support of multiple
government agencies, which have emphasized the need for a conservative
option with less underlying algebraic structure. FrodoKEM has been
recommended as a conservative alternative by the German BSI [BSI],
the French ANSSI [ANSII], and the Dutch NLNCSA and AIVD [NLNCSA, AIVD].
This support ultimately led to the standardization of FrodoKEM by ISO
[ISO18033-2-AMD2]. 

## Protocol-Relevant Considerations

As a KEM, FrodoKEM does not provide authentication for the
communicating parties. Hence, it is important that the protocol using
FrodoKEM allows Bob to validate Alice's public key and allows Alice to
validate Bob's ciphertext. This validation can be performed using some
cryptographic method such as a digital signature or a MAC.

FrodoKEM' specification does not contain any separate algebraic
public-key validation procedure beyond exact parsing and execution of
the specified algorithms. Protocols therefore should treat public keys
as fixed-format opaque byte strings and rely on the surrounding protocol
for origin authentication.

Implementations must perform the full decapsulation verification logic
as specified: decode the received ciphertext components, derive the
candidate message, reconstruct the expected ciphertext under the
regenerated coins, compare the reconstructed values to the received
ones, and apply the fallback secret if the check fails. This logic
is central to FrodoKEM’s CCA-style security.

The byte encoding rules, the separate packing/unpacking byte encoding,
and the matrix encoding and decoding rules are explicitly specified in
the current FrodoKEM Internet-Draft [I-D.FrodoKEM]. Implementations
must follow those rules exactly.

Implementations must validate the exact lengths of public keys, secret
keys and ciphertexts for the selected parameter set before any further
processing. The FrodoKEM Internet-Draft present fixed formats and do
not describe flexible wire encodings for these values.

It is safe to reuse (standard) FrodoKEM public keys for multiple
encapsulations, and doing so produces independent shared secrets for
each ciphertext. However, this does not provide perfect forward
secrecy: if the private key is later compromised, past sessions can
be recovered. Therefore, when a protocol already transmits an
unauthenticated public key (e.g., as part of a handshake), it is
recommended to generate a fresh keypair per session and immediately
delete the private key after decapsulation, which provides perfect
forward secrecy.

## Implementation security

> Patrick: say something about simplicity and ease of implementation,
> and side-channel security. 
> Emphasize need for constant-time implementation for sampling from
> the error distribution, for the decapsulation check, etc.
>
> 


## Public implementations

> Patrick: mention the portable and efficient implementations in C,
> the readable reference implementations in Python, and the functional
> tests and known-answer tests. 
>
> 


# IANA Considerations

This document has no IANA actions.

--- back