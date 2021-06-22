# Charter proposal for an DANISH WG

- Name: DANE AutheNtication for Iot Service Hardening
- Revision: 1.2.0

## Objective

The DANE AutheNtication for Iot Service Hardening (DANISH) WG seeks to
extend DANE to encompass TLS client authentication using certificates.

The WG will also use DANE to establish identities for store and forward of
objects using object security, secured with sender identities.

## Problem statement

The process of establishing trust in public-key-authenticated identity
typically involves the use of a Public Key Infrastructure (PKI), and a
shared PKI root of trust between the parties exchanging public keys. A
Certification Authority (CA) is one example of a PKI which can be used for
establishing trust in public keys.

The DNS namespace, together with DNSSEC, forms the most widely-recognized
namespace and authenticated discovery mechanism on the Internet.
DANE builds on this authenticated discovery mechanism to enable public key-based
TLS authentication which is resilient to impersonation, but only for TLS
server identities.

In response to the challenges related to ambiguity between identities issued
by different CAs, application owners frequently choose to onboard IoT devices
to a single private CA specific to that vertical.
This creates a silo effect where different parts of large deployment can not
communicate.  For instance the heating cooling system of a building can not
authenticate the lighting control system.

Many IoT deployments use some kind of message bus (for instance MQTT) to
exchange data, and there is a strong desire to add object security
to the objects which are exchanged.
While there might be TLS in use for connection security, it does not extend to what is communicated and so does not convey authority assert a reading, while an object security system would provide that.

A DNS name is a useful unique identifier to which humans interact with well,
and which can be used (thanks to DNSSEC and DANE) to attach a key by which to
authenticate the object sender identity.

## Scope of work

DANISH will specify the TLS session and object security use cases and an
architecture describing the primary components and interaction patterns.

DANISH will establish usage conventions for DANE DNS records to represent
client identity for TLS connections and how to perform public key discovery
for object security use cases, like the establishment of object sender
identity.

DANISH will coordinate with the TLS working group to define any required
TLS v1.3 protocol updates required to support client authentication using
DANE.

While modifications to the following standards are not within the scope of
the DANISH charter, the DANISH working group will take care to ensure a
potential path for interoperability with the following standards, enabling
potential future work:SMIMEA (RFC 8162), Proxy headers (RFC 7239), IANA
email authentication headers, and TCP proxy TLVs standardized by haproxy.

In this initial chartering, EAP-TLS and other network level authentication systems are not in scope.

## Deliverables:

* DANISH architecture document (9 months)

* DANE for client certificates (current draft) (6 months)

* DANE for TLS client authentication (current draft) (6 months)



