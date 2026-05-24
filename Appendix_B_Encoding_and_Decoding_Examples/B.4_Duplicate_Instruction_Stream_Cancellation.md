---
title: "B.4. 复制指令与流的取消"
anchor: "B.4_Duplicate_Instruction_Stream_Cancellation"
weight: 11400
rank: "h2"
---

编码器在动态表中对某条目进行复制，随后发送的编码字段组引用了一些动态表条目，其中包含复制出来的那个条目。
携带着编码流数据的数据包受到延误。
在送达该数据包前，解码器取消了流，并通知编码器它没有对编码字段组进行处理。

{{< block_img
indx="Pseudocode_b_4"
src="/RFC9204_Chinese_Simplified/images/Pseudocode_b_4.svg" >}}
