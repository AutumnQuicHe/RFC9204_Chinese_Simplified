---
title: "附录B. 编码和解码样例"
anchor: "Appendix_B_Encoding_and_Decoding_Examples"
weight: 11000
rank: "h1"
---

The following examples represent a series of exchanges between an encoder and a decoder. The exchanges are designed to exercise most QPACK instructions and highlight potentially common patterns and their impact on dynamic table state. The encoder sends three encoded field sections containing one field line each, as well as two speculative inserts that are not referenced.

在接下来的例子中，展现了一系列编码器与解码器间的通信。设计这些通信的目的是将大多数QPACK指令运用起来，并强调也许会很常见的一些模式及其对动态表状态的影响。编码器发送了三个编码字段组，其中每个字段组中包含一条字段行，还试探性地发送了两次没有得到引用的插入。

The state of the encoder's dynamic table is shown, along with its current size. Each entry is shown with the Absolute Index of the entry (Abs), the current number of outstanding encoded field sections with references to that entry (Ref), along with the name and value. Entries above the 'acknowledged' line have been acknowledged by the decoder.

编码器的动态表状态及其当前尺寸如图所示。图示中为每个条目指明了该条目的绝对索引（索引）、引用了该条目且在途的编码字段组数（引用）、该条目的名称，以及该条目的值。在“已确认”一行上方的条目已经得到了解码器的确认。
