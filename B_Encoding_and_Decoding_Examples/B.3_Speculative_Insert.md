---
title: "B.3. 试探插入"
anchor: "B.3_Speculative_Insert"
weight: 11300
rank: "h2"
---

The encoder inserts a header into the dynamic table with a literal name. The decoder acknowledges receipt of the entry. The encoder does not send any encoded field sections.

编码器向动态表插入了一条使用明文名称的标头。
解码器确认接收到该条目。
编码器没有发送任何编码字段组。

{{< block_img
indx="Pseudocode_b_3"
src="/RFC9204_Chinese_Simplified/images/Pseudocode_b_3.svg" >}}
