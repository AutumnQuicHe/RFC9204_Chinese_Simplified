---
title: "4.5.1. 编码字段组的前缀"
anchor: "4.5.1_Encoded_Field_Section_Prefix"
weight: 4510
rank: "h3"
---

每个编码字段组都以两个整型作为前缀。
使用[第4.5.1.1章](#4.5.1.1_Required_Insert_Count)中的编码方法，插入计数下限被编码为一个8位前缀整型。
基点被编码为一个信号比特位（`S`）和一个7位前缀整型的“基点差值”；详见[第4.5.1.2章](#4.5.1.2_Base)。

{{< block_img
indx="Figure_12_Encoded_Field_Section"
title="图12：编码字段组"
src="/RFC9204_Chinese_Simplified/images/Figure_12_Encoded_Field_Section.svg" >}}
