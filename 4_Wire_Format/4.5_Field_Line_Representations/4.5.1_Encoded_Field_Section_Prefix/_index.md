---
title: "4.5.1. 编码字段组的前缀"
anchor: "4.5.1_Encoded_Field_Section_Prefix"
weight: 4510
rank: "h3"
---

Each encoded field section is prefixed with two integers. The Required Insert Count is encoded as an integer with an 8-bit prefix using the encoding described in Section 4.5.1.1. The Base is encoded as a Sign bit ('S') and a Delta Base value with a 7-bit prefix; see Section 4.5.1.2.

每个编码字段组都以两个整型作为前缀。使用[第4.5.1.1章]()中的编码方法，插入计数下限被编码为一个8位前缀整型。基点被编码为一个信号比特位（`S`）和一个7位前缀整型的“基点差值”；详见[第4.5.1.2章]()。

TODO: Figure 12: Encoded Field Section
