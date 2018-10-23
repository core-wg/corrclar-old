---
stand_alone: true
cat: std
updates: 6690, 7252, 7641, 7959, 8132, 8323
pi:
  compact: 'yes'
  text-list-symbols: "-o*+"
  subcompact: 'no'
  sortrefs: 'yes'
  symrefs: 'yes'
  strict: 'yes'
  toc: 'yes'
title: >
  Constrained Application Protocol (CoAP): Corrections and Clarifications
abbrev: Corrections and Clarifications to CoAP
docname: draft-bormann-core-corr-clar
author:
 -
    name: Carsten Bormann
    org: Universität Bremen TZI
    street: Postfach 330440
    city: Bremen
    code: D-28359
    country: Germany
    phone: +49-421-218-63921
    email: cabo@tzi.org

normative:
  RFC6690: link-format
  RFC7252: coap
  RFC7641: observe
  RFC7959: block
  RFC8132: etch
  RFC8323: coap-tcp
informative:
  I-D.ietf-core-too-many-reqs: RC429

--- abstract


RFC 7252 defines the Constrained Application Protocol (CoAP), along
with a number of additional specifications, including RFC 7641, RFC
7959, RFC 8132, and RFC 8323.
RFC 6690 defines the link format that is used in CoAP self-description
documents.

Some parts of the specification may be unclear or even contain errors
that may lead to misinterpretations that may impair interoperability
between different implementations.
The present document provides corrections, additions, and
clarifications to the RFCs cited; this document thus updates these
RFCs.
In addition, other clarifications related to the use of CoAP in other
specifications, including RFC 7390 and RFC 8075, are also provided.

--- middle

# Introduction

{{-coap}} defines the Constrained Application Protocol (CoAP), along
with a number of additional specifications, including {{-observe}},
{{-block}}, {{-etch}}, and {{-coap-tcp}}.
{{-link-format}} defines the link format that is used in CoAP
self-description documents.

During implementation and interoperability testing of these RFCs, and
in their practical use, some ambiguities and common misinterpretations
have been identified, as well as a few errors.

The present document summarizes identified issues and provides
corrections needed for implementations of CoAP to interoperate, i.e.,
it constitutes an update to the RFCs referenced.  This document also
provides other clarifications related to common misinterpretations of
the specification.  References to CoAP should, therefore, also include
this document.

In addition, some clarifications and corrections are also provided for
documents that are related to CoAP, including RFC 7390 and RFC 8075.

## Process

The present document is an Internet-Draft, which is not intended to be
published as an RFC quickly.  Instead, it will be maintained as a
running document of the CoRE WG, probably for a number of years, until
the need for new entries tails off and the document can finally be
published as an RFC.  (This paragraph to be rephrased when that
happens.)

The status of this document as a running document of the WG implies a
consensus process that is applied in making updates to it.  The rest
of this subsection provides more details about this consensus process.
(This is the intended status; currently, the document is an individual submission only.)

(Consensus process TBD, but it will likely be based on an editor's
version in a publicly accessible git repository, as well as periodic
calls for consensus that lead to a new published Internet-Draft;.)

## Terminology

{::boilerplate bcp14}

When a section of this document makes formal corrections, additions
or invalidations to text in a referenced RFC, this is clearly summarized.
The text from the RFC that is being addressed is given and labeled
"INCOMPLETE", "INCORRECT", or "INCORRECT AND INVALIDATED", followed
by the correct text labeled "CORRECTED", where applicable.  When text
is added that does not simply correct text in previous
specifications, it is given with the label "FORMAL ADDITION".

Where a resolution has not yet been agreed, the resolution is marked PENDING.

In this document, a reference to a section in RFC nnnn is written
as RFC nnnn-\<number>, where \<number> is the section number.

# RFC 7252

## RFC7252-5.10.5: Max-Age

In the discussion of {{-RC429}}, a comment was
made that it would be needed to define the point in time relative to
which Max-Age is defined.  A sender might reference it to the time it
actually sends the message containing the option (and paragraph 3 of
RFC7252-5.10.5 indeed requests that Max-Age be updated each time a
message is retransmitted).  The receiver of the message does not have
reliable information about the time of sending, though.  It may
instead reference the Max-Age to the time of reception.  This in
effect extends the time of Max-Age by the latency of the packet.
This extension was deemed acceptable for the purposes of {{-RC429}},
but may be suboptimal when Max-Age is about the lifetime of a response
object.

{: vspace='0'}
INCOMPLETE:
: The value is intended to be current at the time of transmission.

PENDING.

# IANA Considerations

None yet.

(Individual clarifications may contain IANA considerations; these will
then be referenced here.)

# Security Considerations

This document provides a number of corrections and clarifications to
existing RFCs, but it does not make any changes with regard to the security
aspects of the protocol.  As a consequence, the security
considerations of the referenced RFCs apply without additions.

(To be changed when that is no longer true; probably the security
considerations will then be on the individual clarifications.)

--- back

# Acknowledgements
{: numbered='no'}

The present document is modeled after RFC 4815 and the Internet-Drafts
of the ROHC WG that led to it.  Many thanks to the co-chairs of the
ROHC WG and WG members that made this a worthwhile and successful
experiment at the time.

<!--  LocalWords:  interoperate invalidations retransmitted ROHC
 -->
<!--  LocalWords:  suboptimal
 -->
