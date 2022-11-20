---
title: "7.1. 探测动态表的状态"
anchor: "7.1_Probing_Dynamic_Table_State"
weight: 7100
rank: "h2"
---

QPACK reduces the encoded size of field sections by exploiting the redundancy inherent in protocols like HTTP. The ultimate goal of this is to reduce the amount of data that is required to send HTTP requests or responses.

The compression context used to encode header and trailer fields can be probed by an attacker who can both define fields to be encoded and transmitted and observe the length of those fields once they are encoded. When an attacker can do both, they can adaptively modify requests in order to confirm guesses about the dynamic table state. If a guess is compressed into a shorter length, the attacker can observe the encoded length and infer that the guess was correct.

This is possible even over the Transport Layer Security Protocol ([TLS]) and the QUIC Transport Protocol ([QUIC-TRANSPORT]), because while TLS and QUIC provide confidentiality protection for content, they only provide a limited amount of protection for the length of that content.

    Note: Padding schemes only provide limited protection against an attacker with these capabilities, potentially only forcing an increased number of guesses to learn the length associated with a given guess. Padding schemes also work directly against compression by increasing the number of bits that are transmitted.

Attacks like CRIME ([CRIME]) demonstrated the existence of these general attacker capabilities. The specific attack exploited the fact that DEFLATE ([RFC1951]) removes redundancy based on prefix matching. This permitted the attacker to confirm guesses a character at a time, reducing an exponential-time attack into a linear-time attack.
