%%%
title = "Domain Boundaries 2.0 Problem Statement"
abbrev = "DBOUND2 Problem"
docName = "@DOCNAME@"
category = "info"
obsoletes = []
ipr = "trust200902"
area = "Application"
workgroup = "DBOUND2"
submissiontype = "IETF"
keyword = [""]

[seriesInfo]
name = "Internet-Draft"
value = "@DOCNAME@"
stream = "IETF"
status = "informational"

[[author]]
initials = "T."
surname = "Wicinski"
fullname = "Tim Wicinski"
  [author.address]
  email = "tjw.ietf@gmail.com"
  [author.address.postal]
  city = "Elkins"
  region = "WV"
  code = "26241"
  country = "USA"


%%%

.# Abstract

Internet clients attempt to make inferences about the administrative
relationship based on domain names. Currently it is not possible to confirm
organizational boundaries in the DNS.  Current mitigation strategies have
there own issues.  This memo attempts to outline these issues.

{mainmatter}

# Introduction and Motivation {#introduction}

Working off of the earlier problem statement [@?I-D.sullivan-dbound-problem-statement],
which we still consider valid. Various Internet protocols and applications
require some mechanism for determining whether two domain names have some relation.

The concept of an administrative boundary is by definition not present
in the DNS. Relying on the DNS to divine administrative structure thus
renders such solutions unreliable and unnecessarily constrained. For
example, confirming or dismissing a relationship between two domain
names based on the existence of a zone cut or common ancestry is often
unfounded, and the notion of an upward "tree walk" as a search
mechanism is, therefore, unacceptable.

Currently, the most well known solution in existence is the Public
Suffix List (PSL). The PSL is maintained by  and is kept current by
volunteers on a best-effort basis. It contains a list of points in the
hierarchical namespace at which registrations take place, and is used
to identify the boundary between so-called "public" names (below which
registrations can occur, such as ".com" or ".org.uk") and the private
names (organizational names) that domain registrars create within them.
When this list is inaccurate, it exposes a deviation from reality that
degrades service to some and can be exploited by others. As the PSL is
the de-facto resource, and as there is not a more comprehensive,
alternative solution for relationship identification, the PSL has often
been misused to accomplish things beyond its capabilities. For example,
there is no way to confirm the relationship between two domain names --
the PSL may only signal that there is or is not a public boundary
between the two. Additionally, there are questions about the
scalability, central management, and third-party management of the PSL
as it currently exists.


Applications and organizations impose policies and procedures that create additional structure in their use of domain names. This creates many possible relationships that are not evident in the names themselves or in the operational, public representation of the names.

(This document is currently being edited at
https://github.com/moonshiner/draft-tjw-dbound2-problem-statement)

# Terminology {#terminology}

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in BCP 14 [@!RFC2119] [@RFC8174]
when, and only when, they appear in all capitals, as shown here.
DNS terminology is as described in [@?RFC8499].


# Simplifying the list of possible Use Cases

A main topic that immediately arises from this discussion is the replacement
of the Public Suffix List (PSL).  Currently, this document is not looking at
the problem space with regards to it.

From the previous problem statement, the one use case which



## HTTP State management cookies


* Cookies that have the same-site in browsers. For example:

    allowing www.example.com to respond with a set-cookie for example.com
    so \*.example.com will work.

    not allowing example1.co.uk to respond with a set-cookie for example2.co.uk.

* CA wildcards: it's OK to sign a cert for \*.example.co.uk or \*.example.com but not for \.co.uk or \*.com.


Other applications and organizations impose policies and procedures that
create additional structure to express many possible relationships,
such as in first-party-sets or IDN-UA. These are not always evident
in the names themselves, and any solutions developed here may or may
not suit these existing policies and procedures.


## Service Boundaries in shared cloud environments

A public cloud provider may have a large number of boundaries they need
to publish.  Taking an
example resource within an example service, that resource might have a
domain name that follows the below pattern (2LD may vary):

   "resource-id.cluster-id.servicename.region-name.example.com"

With the current PSL, the need may exist to publish 1+ records per region per
service. If there are many services across many more regions, these updates
do not scale. Putting this information into DNS allows us to publish records,
without manual updates.

## Network resource boundaries in shared cloud environments

Network suffixes and resouces that are public, but not routable or resolvable
outside of one's network (public-like-PSL, not public-like-pool). A good
example is an internal zone within a virtual private
clouds (VPCs).

VPCs are resources customers can create, which reserves
them a logically-isolated portion of AWS's network. Within each VPC,
there is a VPC-internal DNS zone which contains DNS records for
resources within the VPC (suffix zone of "compute.internal" or
equivalent), which is separated per-VPC. Every network interface in a
VPC will have an associated per-interface record in this zone (for VPCs
using a default configuration).

These customers may chose to peer their VPC with another customer,
and these VPC-internal zone would now have multiple different customers
operating within it.


* Linking domains together

In terms of specific use cases, within the realm of email there is a
desire to link an arbitrary fully-qualified domain name (FQDN) to the
organizational domain name (at some point in the namespace above it),
in order to identify a deterministic location where some sort of
statement of policy regarding that FQDN can be found.

There is another growing use case within organizations that need to identify
relationships between different FQDNs, but also different top level
domains. However, there is also desire to reliably identify relationships
outside of the realm and constraints of the namespace tree.



# Security Considerations

None at this time.


# IANA Considerations

None at this time.

{backmatter}
# Acknowledgements

The author leans heavily on the initial problem statement and thanks Andrew
Sullivan, John Levine, Murray Kucherawy and Paul Vixie for comments and
suggestions.

# Appendix


{numbered="false"}

# Acknowledgements {#acknowledgements}

