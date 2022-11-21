---
title: "附录B. 编码和解码样例"
anchor: "Appendix_B_Encoding_and_Decoding_Examples"
weight: 11000
rank: "h1"
---

The following examples represent a series of exchanges between an encoder and a decoder. The exchanges are designed to exercise most QPACK instructions and highlight potentially common patterns and their impact on dynamic table state. The encoder sends three encoded field sections containing one field line each, as well as two speculative inserts that are not referenced.

The state of the encoder's dynamic table is shown, along with its current size. Each entry is shown with the Absolute Index of the entry (Abs), the current number of outstanding encoded field sections with references to that entry (Ref), along with the name and value. Entries above the 'acknowledged' line have been acknowledged by the decoder.
