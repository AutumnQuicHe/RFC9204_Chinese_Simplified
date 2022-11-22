---
title: "4.5. 字段行的指称"
anchor: "4.5_Field_Line_Representations"
weight: 4500
rank: "h2"
---

An encoded field section consists of a prefix and a possibly empty sequence of representations defined in this section. Each representation corresponds to a single field line. These representations reference the static table or the dynamic table in a particular state, but they do not modify that state.

编码字段组由一个前缀和一些定义在该组中的指称序列（可以是空序列）组成。
每条指称都对应着一条字段行。
这些指称会引用静态表或特定状态下的动态表，但它们不会修改动态表的状态。

Encoded field sections are carried in frames on streams defined by the enclosing protocol.

编码字段组是在由封装协议定义的流上，用帧结构来传递的。
