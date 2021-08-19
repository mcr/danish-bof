# Charter proposal for an DANCE WG

- Name: DANE Authentication for Network Clients Everywhere (DANCE) [TBD: verify]
- Revision: 1.2.0

## Objective

The DANE Authentication for Network Clients Everywhere (DANCE) WG seeks to
extend DANE to encompass TLS client authentication using certificates or Raw Public Keys (RPK).

## Problem Statement

The process of establishing trust in public-key-authenticated identity
typically involves the use of a Public Key Infrastructure (PKI), and a
shared PKI root of trust between the parties exchanging public keys. A
Certification Authority (CA) is one example of a root of trust for a
PKI, which can be then used for establishing trust in certified public
keys.

The DNS namespace, together with DNSSEC, forms the most widely-recognized
namespace and authenticated lookup mechanism on the Internet.
DANE builds on this authenticated lookup mechanism to enable public key-based
TLS authentication which is resilient to impersonation, but only
for TLS server identities.
However, DANE did not define authentication for TLS client identities.

<!-- defines a lookup mechanism for TLS -->
<!-- server identities and a published trust-path to their public key. -->

In response to the challenges related to ambiguity between identically
named identities issued by different CAs, application owners
frequently choose to onboard client identities to a single private PKI
with a limited CA set that is specific to that vertical.  This creates
a silo effect where different parts of large deployment can not
communicate.  Examples of where DANCE could be useful includes SMTP
transport client authentication, authentication of DNS authoritative
server to server zone file transfers over TLS, authentication to DNS
recursive servers, and Internet of Things (IoT) device identification.

## Scope of work

DANCE will specify the TLS client authentication use cases and an
architecture describing the primary components and interaction patterns.

DANCE will define how DNS DANE records will represent client
identities for TLS connections.

DANCE will coordinate with the TLS working group to define any
required TLS protocol updates required to support client
authentication using DANE.

The DANCE scope of work will be initially limited to just TLS client
authentication.  Future work may include using client identifiers for
other tasks including object security, or authenticating to other
protocols.

## Deliverables:

* DANCE architecture and use cases (IoT, SMTP client,
  authentication to DNS services, ...) document (9 months)

* DANE client authentication and publication practices (current draft) (6 months)

* A TLS extension to indicate DANE identification capability and the
  client's DANE identity name (current draft) (6 months)


