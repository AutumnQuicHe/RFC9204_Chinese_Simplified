---
title: "7.1. 探测动态表的状态"
anchor: "7.1_Probing_Dynamic_Table_State"
weight: 7100
rank: "h2"
---

QPACK reduces the encoded size of field sections by exploiting the redundancy inherent in protocols like HTTP. The ultimate goal of this is to reduce the amount of data that is required to send HTTP requests or responses.

QPACK通过利用HTTP等协议中固有的冗余来降低字段组经过编码后的尺寸。这么做的终极目标是降低发送HTTP请求或响应所需的数据量。

The compression context used to encode header and trailer fields can be probed by an attacker who can both define fields to be encoded and transmitted and observe the length of those fields once they are encoded. When an attacker can do both, they can adaptively modify requests in order to confirm guesses about the dynamic table state. If a guess is compressed into a shorter length, the attacker can observe the encoded length and infer that the guess was correct.

只要攻击者既有能力定义编码和传输的字段，又能够观测这些字段经过编码后的长度，用于编码头部和挂载字段的压缩上下文就可能被攻击者探测。这样的攻击者可以适当修改请求，从而确信关于动态表状态的猜测。如果某个猜测被压缩为了更短的长度，那么攻击者就能够观测编码后的长度并且推断出该猜测是正确的。

This is possible even over the Transport Layer Security Protocol ([TLS]) and the QUIC Transport Protocol ([QUIC-TRANSPORT]), because while TLS and QUIC provide confidentiality protection for content, they only provide a limited amount of protection for the length of that content.

即便底层是传输层安全协议（详见《[TLS]()》）和QUIC传输协议（详见《[QUIC传输]()》），这种做法也是可行的，因为尽管TLS和QUIC为其内容提供可信度保护，但是它们为内容的长度信息提供的保护却有限。

    Note: Padding schemes only provide limited protection against an attacker with these capabilities, potentially only forcing an increased number of guesses to learn the length associated with a given guess. Padding schemes also work directly against compression by increasing the number of bits that are transmitted.

    注意：面对具有上述能力的攻击者，填充的策略只能提供有限的保护，最多就是增加攻击者为了判断某次猜测所对应的长度所需的尝试次数。填充还会因为增加传输数据量而与压缩的目的背道而驰。

Attacks like CRIME ([CRIME]) demonstrated the existence of these general attacker capabilities. The specific attack exploited the fact that DEFLATE ([RFC1951]) removes redundancy based on prefix matching. This permitted the attacker to confirm guesses a character at a time, reducing an exponential-time attack into a linear-time attack.

形如CRIME（详见《[CRIME]()》）的攻击说明了此类常见的攻击能力的可行性。特定的攻击还会利用DEFLATE（详见《[RFC1951]()》)基于前缀匹配来降低冗余的事实。这使得攻击者能够一次验证对一个字符的猜测，将需要指数时间的攻击降低为线性时间。
