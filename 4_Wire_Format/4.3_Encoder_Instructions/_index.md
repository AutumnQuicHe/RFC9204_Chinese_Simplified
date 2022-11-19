---
title: "4.3. 编码指令"
anchor: "4.3_Encoder_Instructions"
weight: 4300
rank: "h2"
---

An encoder sends encoder instructions on the encoder stream to set the capacity of the dynamic table and add dynamic table entries. Instructions adding table entries can use existing entries to avoid transmitting redundant information. The name can be transmitted as a reference to an existing entry in the static or the dynamic table or as a string literal. For entries that already exist in the dynamic table, the full entry can also be used by reference, creating a duplicate entry.

编码器在编码流上发送编码指令，从而设置动态表容量，以及添加动态表条目。添加条目的指令中可以使用现有条目，以避免传输冗余信息。名称可以使用引用静态表或动态表中已有条目的方式传输，或者以字符串字面量的方式传输。对于已经出现在动态表中的条目，还可以对其进行完整引用，创建出重复的条目。
