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
role = "editor"
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

# Introduction {#introduction}

Working off of the earlier problem statement [@?I-D.sullivan-dbound-problem-statement],
which we still consider valid.


# Terminology {#terminology}

The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD",
"SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this
document are to be interpreted as described in BCP 14 [@!RFC2119] [@RFC8174]
when, and only when, they appear in all capitals, as shown here.
DNS terminology is as described in [@?RFC8499].

{backmatter}

# Previous Use Cases


The use cases which involve use of the public suffix list, summarized from
the initial problem statement:

* HTTP State management cookies

* User interface indicators

* Setting the document.domain property

* Email authentication mechanisms

* SSL and TLS certificates

* HSTS and Public Key Pinning

* Linking domains together

While all of these are very important to solve, part of the issue with
the first attempt to address this was overreaching goals.  The suggestion is
to initially limit the list to a subset, such as these:

* HTTP State management cookies

* SSL and TLS certificates

* HSTS and Public Key Pinning

# Replicating the Public Suffix List

A main topic that immediately arises from this discussion is the replacement
of the Public Suffix List (PSL).  What does need to be quantified and
understood is the 1) workload needed to update the PSL;  2) how much time
is involved with technical escalations; and 3) the quality of the existing
data in the PSL.  Creating an IANA registry to track such changes could
incur a large workload demand upon IANA staff, and this will need to be
understood.

# Solution Space is a Problem Space

The problem requires solutions which are both static lists and DNS zone
data that can be enumerated. Both must be addressed in understanding
the problem.

# Security Considerations

None at this time.


# IANA Considerations

None at this time.

# Acknowledgements

The author leans heavily on the initial problem statement and thanks Andrew
Sullivan, John Levine, Murray Kucherawy and Paul Vixie for comments and
suggestions.

# Appendix


{numbered="false"}

# Acknowledgements {#acknowledgements}

