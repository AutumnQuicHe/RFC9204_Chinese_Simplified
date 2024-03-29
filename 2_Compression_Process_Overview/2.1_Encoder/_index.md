---
title: "2.1. 编码器"
anchor: "2.1_Encoder"
weight: 2100
rank: "h2"
---

编码器通过为字段组中的每条字段行创建一条索引指称或内联指称的方法，将头部或挂载转换成一系列指称，详见[第4.5章](#4.5_Field_Line_Representations)。
索引指称通过将明文的名称或值替换为一个静态表或动态表的索引，从而取得高压缩率。
引用静态表和明文指称不需要任何动态状态，也不存在队头阻塞的风险。
若编码器尚未收到一个表明在解码器中可以访问该条目的确认回复，则此时引用动态表存在队头阻塞的风险。

编码器{{< req_level MAY >}}向其选择的动态表插入任意条目，而不限于其正在压缩的字段行。

QPACK会维持每个字段组内的字段行的顺序。
编码器{{< req_level MUST >}}以在字段组中出现的顺序发射字段指称。

对于可选的状态追踪特性，QPACK在设计上将此负担放在编码器中，使得解码器的实现相对简单。
