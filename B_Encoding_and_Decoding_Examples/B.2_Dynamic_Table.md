---
title: "B.2. 动态表"
anchor: "B.2_Dynamic_Table"
weight: 11200
rank: "h2"
---

编码器设置动态表容量，插入一条使用了动态索引名称的标头，再发送了一个指向该新条目的编码字段组（其解码可能受到阻塞）。
解码器对编码字段组的处理进行确认，这隐式地确认了截至插入计数下限的所有动态表插入均已完成。

{{< block_img
indx="Pseudocode_b_2"
src="/RFC9204_Chinese_Simplified/images/Pseudocode_b_2.svg" >}}
