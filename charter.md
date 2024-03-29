# Charter proposal for an DANISH WG

- Name: DANE AutheNtication for Iot Service Hardening
- Revision: 1.2.0

## Objective

The DANE AutheNtication for Iot Service Hardening (DANISH) WG seeks to
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
named identities issued
by different CAs, application owners frequently choose to onboard IoT
device's client identities
to a single private PKI with a limited CA set that is specific to that vertical.
This creates a silo effect where different parts of large deployment can not
communicate.  For instance the heating/cooling system of a building
wishing to turn lights off to reduce room temperatures can not
authenticate to the lighting control system.

## Scope of work

DANISH will specify the TLS client authentication use case and an
architecture describing the primary components and interaction patterns.

DANISH will establish usage conventions for DANE DNS records to represent
client identities for TLS connections. 

DANISH will coordinate with the TLS working group to define any required
TLS protocol updates required to support client authentication using
DANE.

Future work may include using client identifiers for other tasks including object security, or authenticating to other protocol services.
The DANISH working group will take care to ensure a
potential path for interoperability, enabling these potential future directions.

## Deliverables:

* DANISH architecture document (9 months)

* DANE for device certificates (current draft) (6 months)

* DANE for TLS client authentication (current draft) (6 months)


