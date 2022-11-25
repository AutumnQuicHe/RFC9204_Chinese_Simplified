---
title: "3.2. 动态表"
anchor: "3.2_Dynamic_Table"
weight: 3200
rank: "h2"
---

The dynamic table consists of a list of field lines maintained in first-in, first-out order. A QPACK encoder and decoder share a dynamic table that is initially empty. The encoder adds entries to the dynamic table and sends them to the decoder via instructions on the encoder stream; see Section 4.3.

动态表由一组按照先进先出顺序维护的字段行组成。
QPACK编码器和解码器共享一张动态表，该表初始为空。
编码器项动态表添加条目，并在编码流上通过指令向解码器发送这些条目；详见[第4.3章](#4.3_Encoder_Instructions)。

The dynamic table can contain duplicate entries (i.e., entries with the same name and same value). Therefore, duplicate entries MUST NOT be treated as an error by the decoder.

动态表中可以包含重复的条目（也就是具有相同名称和相同值的条目）。
因此，条目重复的情况{{< req_level MUST_NOT >}}被解码器视作错误。

Dynamic table entries can have empty values.

动态表条目的值可以为空。
