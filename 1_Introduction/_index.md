---
title: "1. 引言"
anchor: "Intruduction"
weight: 1000
rank: "h1"
---

QUIC传输协议（[QUIC传输](../RFC9000_Chinese_Simplified)）设计的目的就是为了支持HTTP语义，而且其设计将HTTP/2（[HTTP/2](https://www.rfc-editor.org/info/rfc9113)）的许多特性也包括进去了。
HTTP/2使用HPACK（[RFC7541](https://www.rfc-editor.org/info/rfc7541)）压缩头部和挂载字段。
如果将HPACK直接应用于HTTP/3（[HTTP/3](../RFC9114_Chinese_Simplified)）的话，那么会引入头部字段的队头阻塞问题，因为其设计是基于所有帧的所有流都是有序的这一假设之上的。

QPACK复用了HPACK的核心概念，但是在这之上做了重新设计以支持在乱序传递时的正确性，并在实现上保持灵活性以取得在队头阻塞与最佳压缩比之间的弹性平衡。
设计目标是在相同的损耗情况下，尽可能接近HPACK的压缩效率的同时，大幅降低队头阻塞。
