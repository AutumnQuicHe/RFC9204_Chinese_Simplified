---
title: "B.2. 动态表"
anchor: "B.2_Dynamic_Table"
weight: 11200
rank: "h2"
---

The encoder sets the dynamic table capacity, inserts a header with a dynamic name reference, then sends a potentially blocking, encoded field section referencing this new entry. The decoder acknowledges processing the encoded field section, which implicitly acknowledges all dynamic table insertions up to the Required Insert Count.

编码器设置动态表容量，插入一条使用了动态索引名称的标头，再发送了一个指向该新条目的编码字段组（其解码可能受到阻塞）。解码器对编码字段组的处理进行确认，这隐式地确认了截至插入计数下限的所有动态表插入均已完成。

TODO: 图示
