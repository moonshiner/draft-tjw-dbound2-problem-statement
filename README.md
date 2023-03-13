```




DBOUND2                                                 T. Wicinski, Ed.
Internet-Draft                                             13 March 2023
Intended status: Informational                                          
Expires: 14 September 2023


                Domain Boundaries 2.0 Problem Statement
                 draft-tjw-dbound2-problem-statement-00

Abstract

   Internet clients attempt to make inferences about the administrative
   relationship based on domain names.  Currently it is not possible to
   confirm organizational boundaries in the DNS.  Current mitigation
   strategies have there own issues.  This memo attempts to outline
   these issues.

Status of This Memo

   This Internet-Draft is submitted in full conformance with the
   provisions of BCP 78 and BCP 79.

   Internet-Drafts are working documents of the Internet Engineering
   Task Force (IETF).  Note that other groups may also distribute
   working documents as Internet-Drafts.  The list of current Internet-
   Drafts is at https://datatracker.ietf.org/drafts/current/.

   Internet-Drafts are draft documents valid for a maximum of six months
   and may be updated, replaced, or obsoleted by other documents at any
   time.  It is inappropriate to use Internet-Drafts as reference
   material or to cite them other than as "work in progress."

   This Internet-Draft will expire on 14 September 2023.

Copyright Notice

   Copyright (c) 2023 IETF Trust and the persons identified as the
   document authors.  All rights reserved.

   This document is subject to BCP 78 and the IETF Trust's Legal
   Provisions Relating to IETF Documents (https://trustee.ietf.org/
   license-info) in effect on the date of publication of this document.
   Please review these documents carefully, as they describe your rights
   and restrictions with respect to this document.  Code Components
   extracted from this document must include Revised BSD License text as
   described in Section 4.e of the Trust Legal Provisions and are
   provided without warranty as described in the Revised BSD License.




Wicinski                Expires 14 September 2023               [Page 1]

Internet-Draft               DBOUND2 Problem                  March 2023


Table of Contents

   1.  Introduction  . . . . . . . . . . . . . . . . . . . . . . . .   2
   2.  Terminology . . . . . . . . . . . . . . . . . . . . . . . . .   2
   3.  Normative References  . . . . . . . . . . . . . . . . . . . .   2
   4.  Informative References  . . . . . . . . . . . . . . . . . . .   2
   Appendix A.  Previous Use Cases . . . . . . . . . . . . . . . . .   3
   Appendix B.  Replicating the Public Suffix List . . . . . . . . .   3
   Appendix C.  Solution Space is a Problem Space  . . . . . . . . .   4
   Appendix D.  Security Considerations  . . . . . . . . . . . . . .   4
   Appendix E.  IANA Considerations  . . . . . . . . . . . . . . . .   4
   Appendix F.  Acknowledgements . . . . . . . . . . . . . . . . . .   4
   Appendix G.  Appendix . . . . . . . . . . . . . . . . . . . . . .   4
   Acknowledgements  . . . . . . . . . . . . . . . . . . . . . . . .   4
   Author's Address  . . . . . . . . . . . . . . . . . . . . . . . .   4

1.  Introduction

   Working off of the earlier problem statement
   [I-D.sullivan-dbound-problem-statement], which we still consider
   valid.

2.  Terminology

   The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT",
   "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and
   "OPTIONAL" in this document are to be interpreted as described in BCP
   14 [RFC2119] [RFC8174] when, and only when, they appear in all
   capitals, as shown here.  DNS terminology is as described in
   [RFC8499].

3.  Normative References

   [RFC2119]  Bradner, S., "Key words for use in RFCs to Indicate
              Requirement Levels", BCP 14, RFC 2119,
              DOI 10.17487/RFC2119, March 1997,
              <https://www.rfc-editor.org/info/rfc2119>.

4.  Informative References

   [I-D.sullivan-dbound-problem-statement]
              Sullivan, A., Hodges, J., and J. R. Levine, "DBOUND: DNS
              Administrative Boundaries Problem Statement", Work in
              Progress, Internet-Draft, draft-sullivan-dbound-problem-
              statement-02, 18 February 2016,
              <https://datatracker.ietf.org/doc/html/draft-sullivan-
              dbound-problem-statement-02>.




Wicinski                Expires 14 September 2023               [Page 2]

Internet-Draft               DBOUND2 Problem                  March 2023


   [RFC8174]  Leiba, B., "Ambiguity of Uppercase vs Lowercase in RFC
              2119 Key Words", BCP 14, RFC 8174, DOI 10.17487/RFC8174,
              May 2017, <https://www.rfc-editor.org/info/rfc8174>.

   [RFC8499]  Hoffman, P., Sullivan, A., and K. Fujiwara, "DNS
              Terminology", BCP 219, RFC 8499, DOI 10.17487/RFC8499,
              January 2019, <https://www.rfc-editor.org/info/rfc8499>.

Appendix A.  Previous Use Cases

   The use cases which involve use of the public suffix list, summarized
   from the initial problem statement:

   *  HTTP State management cookies

   *  User interface indicators

   *  Setting the document.domain property

   *  Email authentication mechanisms

   *  SSL and TLS certificates

   *  HSTS and Public Key Pinning

   *  Linking domains together

   While all of these are very important to solve, part of the issue
   with the first attempt to address this was overreaching goals.  The
   suggestion is to initially limit the list to a subset, such as these:

   *  HTTP State management cookies

   *  SSL and TLS certificates

   *  HSTS and Public Key Pinning

Appendix B.  Replicating the Public Suffix List

   A main topic that immediately arises from this discussion is the
   replacement of the Public Suffix List (PSL).  What does need to be
   quantified and understood is the 1) workload needed to update the
   PSL; 2) how much time is involved with technical escalations; and 3)
   the quality of the existing data in the PSL.  Creating an IANA
   registry to track such changes could incur a large workload demand
   upon IANA staff, and this will need to be understood.





Wicinski                Expires 14 September 2023               [Page 3]

Internet-Draft               DBOUND2 Problem                  March 2023


Appendix C.  Solution Space is a Problem Space

   The problem requires solutions which are both static lists and DNS
   zone data that can be enumerated.  Both must be addressed in
   understanding the problem.

Appendix D.  Security Considerations

   None at this time.

Appendix E.  IANA Considerations

   None at this time.

Appendix F.  Acknowledgements

   The author leans heavily on the initial problem statement and thanks
   Andrew Sullivan, John Levine, Murray Kucherawy and Paul Vixie for
   comments and suggestions.

Appendix G.  Appendix

Acknowledgements

Author's Address

   Tim Wicinski (editor)
   Elkins, WV 26241
   United States of America
   Email: tjw.ietf@gmail.com





















Wicinski                Expires 14 September 2023               [Page 4]
```
