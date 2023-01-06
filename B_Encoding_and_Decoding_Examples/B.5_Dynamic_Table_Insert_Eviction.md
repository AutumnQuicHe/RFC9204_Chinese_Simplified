---
title: "B.5. 动态表的插入与驱逐"
anchor: "B.5_Dynamic_Table_Insert_Eviction"
weight: 11500
rank: "h2"
---

编码器向动态表插入了另一个标头，这么做会驱逐最先被插入的那个条目。
编码器没有发送任何编码字段组。

{{< block_img
indx="Pseudocode_b_5"
src="/RFC9204_Chinese_Simplified/images/Pseudocode_b_5.svg" >}}
