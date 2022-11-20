---
title: "7. 关于安全性的考量"
anchor: "7_Security_Considerations"
weight: 7000
rank: "h1"
---

This section describes potential areas of security concern with QPACK:

本章介绍了有关QPACK安全性的几个担忧：

* Use of compression as a length-based oracle for verifying guesses about secrets that are compressed into a shared compression context.

* 利用压缩后的数据长度验证秘密值是否位于共享压缩上下文中的猜想。

* Denial of service resulting from exhausting processing or memory capacity at a decoder.

* 通过耗尽解码器处理资源或内存容量的拒绝服务攻击。
