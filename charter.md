# Charter proposal for an DANISH WG

- Name: DANE AutheNtication for Iot Service Hardening
- Revision: 1.1.0

## Objective

The now closed DANE working group (WG) produced a mechanism that supported
authentication of TLS server identities via a DNSSEC-secured
infrastructure.  Operational experience with DANE has validated the utility
of a DNS-enabled mechanism for discovering authenticated keys, but has also
shown that reliance on DNSSEC is a significant barrier to adoption.

The DANE AutheNtication for Iot Service Hardening (DANISH) WG seeks to
extend DANE to encompass TLS client and message sender identities. DANISH
will also define a mechanism for messaging use cases that allows DANE DNS
record types to be secured by the Web PKI as a transition strategy for
domain owners who have not yet implemented a DNSSEC-based trust model.

## Problem Statement

The process of establishing trust in public-key-authenticated identity
typically involves the use of a Public Key Infrastructure (PKI), and a
shared PKI root of trust between the parties exchanging public keys. A
Certificate Authority (CA) is one example of a PKI which can be used for
establishing trust in public keys. CAs only guarantee the uniqueness of an
identity’s name within the context of the CA, and multiple CAs may sign
certificates for different entities bearing the same name. DNSSEC is
another PKI, which is bound to the DNS namespace.

The DNS namespace, together with DNSSEC, forms the most widely-recognized
namespace and authenticated discovery mechanism on the Internet. DANE
builds on this authenticated discovery mechanism to enable public key-based
TLS authentication which is resilient to impersonation, but only for TLS
server identities.

The use of CA-based PKI alone for client and message sender authentication
creates the possibility of naming collisions when multiple CAs are trusted
within the same application. In response to the challenges related to
ambiguity between identities issued by different CAs, application owners
frequently choose to onboard IoT devices to a single CA. This process of
credential issuance can be time-consuming, which is further exacerbated by
the sheer number of entities participating in large-scale IoT deployments.

Expanding the use cases for DANE to support the representation of TLS
client and message sender identities will enable unambiguous authentication
across CAs, for client/server TLS sessions as well as message-oriented
information flows.

The greatest barrier to DANE adoption has been the DNSSEC requirement.
DANISH will provide a method of certificate and trust chain discovery for
private PKIs, to enable the messaging security use case, in a manner which
will work securely in the absence of DNSSEC. This allows for a gradual DANE
adoption where DNSSEC is not in the initial set of requirements.

## Scope of work
DANISH will specify the TLS session and message security use cases and an
architecture describing the primary components and interaction patterns.

DANISH will establish usage conventions for DANE DNS records to represent
client identity for TLS connections and how to perform public key discovery
for message security use cases, like the establishment of message sender
identity.

DANISH will coordinate with the TLS working group to define any required
TLS v1.3 protocol updates required to support client authentication using
DANE.

DANISH will standardize a protocol and specify operational recommendations
for the use of Web PKI to authenticate the discovery of private PKI
certificates and trust chains via DANE DNS record types, in the absence of
DNSSEC, in support of the message security use case.

While modifications to the following standards are not within the scope of
the DANISH charter, the DANISH working group will take care to ensure a
potential path for interoperability with the following standards, enabling
potential future work:SMIMEA (RFC 8162), Proxy headers (RFC 7239), IANA
email authentication headers, and TCP proxy TLVs standardized by haproxy.

## Deliverables:

* DANISH architecture document (9 months)
DANE for client certificates (current draft) (6 months)
DANE for TLS client authentication (current draft) (6 months)
DANE Transitional Mode Definition and Operational Guidance (non-DNSSEC) (1 year)
